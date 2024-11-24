# Tailscale QEMU Runner Action

A GitHub Action to start an ephemeral QEMU-based runner VM via Tailscale.

## How to use

You'll need the following things:

- A [Tailscale](https://tailscale.com/kb/1151/what-is-tailscale) tailnet with one or more machines with QEMU installed.
- A [OAuth client](https://tailscale.com/kb/1215/oauth-clients#setting-up-an-oauth-client) configured on the tailnet.
- [Tailscale SSH](https://tailscale.com/kb/1193/tailscale-ssh) needs to be enabled on the tailnet, with [appropriate `accept` ACLs](https://tailscale.com/kb/1193/tailscale-ssh#action) configured. `accept` must be used for SSH ACLs, `check` is **not** supported. Tailscale ephemeral nodes are automatically tagged with the value from `ts-tag`, this tag can be used with ACLs.
- A GitHub [Personal Access Token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#about-personal-access-tokens) with appropriate permissions to [request a runner registration token](https://docs.github.com/en/rest/actions/self-hosted-runners?apiVersion=2022-11-28#create-a-registration-token-for-a-repository) via the GitHub REST API.

## Example workflow

At a minimum, your workflow should look like this:

```yaml
jobs:
  create-runner:
    name: Create self-hosted Actions runner
    runs-on: ubuntu-latest
    steps:
      - name: Create self-hosted Actions runner
        uses: MattKobayashi/tailscale-qemu-runner-action@v1.0.0
        with:
          gh-api-token: ${{ secrets.GH_API_TOKEN }}
          ssh-host: 192.0.2.1
          ssh-user: matthew
          ts-oauth-client-id: ${{ secrets.TS_OAUTH_CLIENT_ID }}
          ts-oauth-secret: ${{ secrets.TS_OAUTH_SECRET }}
```

Ephemeral runners will remove themselves after completing a single job in a workflow. If you have multiple jobs to execute, a matrix can be used to spawn multiple runners:

> [!CAUTION]
> Be mindful of resource allocation when spawning multiple runners. Appropriate values for the `gha-runner-cpus` and `gha-runner-mem` inputs is strongly recommended.

```yaml
jobs:
  create-runner:
    name: Create self-hosted runner VM
    runs-on: ubuntu-latest
    strategy:
      fail-fast: false
      max-parallel: 1
      matrix:
        runner-name: [test]
    steps:
      - name: Create self-hosted Actions runner
        uses: MattKobayashi/tailscale-qemu-runner-action@v1.0.0
        with:
          gh-api-token: ${{ secrets.GH_API_TOKEN }}
          ssh-host: 192.0.2.1
          ssh-user: matthew
          ts-oauth-client-id: ${{ secrets.TS_OAUTH_CLIENT_ID }}
          ts-oauth-secret: ${{ secrets.TS_OAUTH_SECRET }}
```

## Considerations

- QEMU image files are stored in `/tmp/actions-runners/`. If you're processing many jobs, this directory can grow quite large. It's recommended to create a cronjob on the QEMU host to regularly clean up this directory. `/tmp` is also cleared when the host is rebooted.
- Container-based tasks are fully supported.
- The default values for `gha-runner-cpus` and `gha-runner-mem` match those of GitHub's hosted runners, however these values are also quite large. It is important to be mindful of this, and adjust these values as necessary.

## Inputs

### `gh-api-token`

**Required** A GitHub Personal Access Token with `repo` scope, or a fine-grained access token with `administration:write` permission.

### `gha-runner-cpus`

The number of CPUs to allocate to the self-hosted runner VM. Defaults to `4`.

### `gha-runner-mem`

The amount of memory to allocate to the self-hosted runner VM in megabytes. Optionally, a suffix of “M” or “G” can be used to signify a value in megabytes or gigabytes respectively. Defaults to `16G`.

### `gha-runner-sha`

The SHA256 checksum of the self-hosted runner tarball. Defaults to the SHA256 checksum for the tarball version specified in `gha-runner-version`.

### `gha-runner-version`

The version of self-hosted runner to install. Defaults to `2.321.0`.

### `ssh-keyscan-timeout`

The timeout value for `ssh-keyscan` in seconds. Defaults to `60`.

### `ssh-host`

**Required** The Tailscale hostname or Tailscale IP address of your QEMU host.

### `ssh-user`

**Required** The SSH username to use when logging into your QEMU host.

### `ts-oauth-client-id`

**Required** Your Tailscale OAuth Client ID.

### `ts-oauth-secret`

**Required** Your Tailscale OAuth Client Secret.

### `ts-tag`

A unique tag to apply to ephemeral Tailscale nodes. Defaults to `github-actions`.

### `ts-version`

The Tailscale client version to use. Defaults to `1.76.6`.
