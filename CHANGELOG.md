# Changelog

## [1.6.1](https://github.com/MattKobayashi/tailscale-qemu-runner-action/compare/v1.6.0...v1.6.1) (2024-12-10)


### Bug Fixes

* **action:** Remove ssh-keyscan ([#35](https://github.com/MattKobayashi/tailscale-qemu-runner-action/issues/35)) ([d3c714d](https://github.com/MattKobayashi/tailscale-qemu-runner-action/commit/d3c714d90f740a22db5db6054ffa247fb1690cbc))

## [1.6.0](https://github.com/MattKobayashi/tailscale-qemu-runner-action/compare/v1.5.6...v1.6.0) (2024-12-09)


### Features

* **action:** Install `docker-compose-plugin` ([#33](https://github.com/MattKobayashi/tailscale-qemu-runner-action/issues/33)) ([54f64e9](https://github.com/MattKobayashi/tailscale-qemu-runner-action/commit/54f64e927c116003abf02fecf44f17deecf1a232))

## [1.5.6](https://github.com/MattKobayashi/tailscale-qemu-runner-action/compare/v1.5.5...v1.5.6) (2024-12-09)


### Bug Fixes

* **action:** Clear local APT lists ([#31](https://github.com/MattKobayashi/tailscale-qemu-runner-action/issues/31)) ([3f63150](https://github.com/MattKobayashi/tailscale-qemu-runner-action/commit/3f631505e8b13786cb4f73d6f1accedcd6c129f7))

## [1.5.5](https://github.com/MattKobayashi/tailscale-qemu-runner-action/compare/v1.5.4...v1.5.5) (2024-12-09)


### Bug Fixes

* **action:** Use --no-install-recommends ([#28](https://github.com/MattKobayashi/tailscale-qemu-runner-action/issues/28)) ([baaa037](https://github.com/MattKobayashi/tailscale-qemu-runner-action/commit/baaa0379c0cd82f724d7614689470bdbed443e82))

## [1.5.4](https://github.com/MattKobayashi/tailscale-qemu-runner-action/compare/v1.5.3...v1.5.4) (2024-12-04)


### Bug Fixes

* **action:** Fork QEMU to background ([#26](https://github.com/MattKobayashi/tailscale-qemu-runner-action/issues/26)) ([c28772e](https://github.com/MattKobayashi/tailscale-qemu-runner-action/commit/c28772e0cc38df4bc42f671280906fad4d03b8db))

## [1.5.3](https://github.com/MattKobayashi/tailscale-qemu-runner-action/compare/v1.5.2...v1.5.3) (2024-11-29)


### Bug Fixes

* **action:** Install build-essential ([#24](https://github.com/MattKobayashi/tailscale-qemu-runner-action/issues/24)) ([486baae](https://github.com/MattKobayashi/tailscale-qemu-runner-action/commit/486baae16410f6aec048de3e7af50064eecb58c3))

## [1.5.2](https://github.com/MattKobayashi/tailscale-qemu-runner-action/compare/v1.5.1...v1.5.2) (2024-11-28)


### Bug Fixes

* **action:** Create /opt/hostedtoolcache ([#22](https://github.com/MattKobayashi/tailscale-qemu-runner-action/issues/22)) ([ffac755](https://github.com/MattKobayashi/tailscale-qemu-runner-action/commit/ffac755351720630d177f0ef875278862abe71ba))

## [1.5.1](https://github.com/MattKobayashi/tailscale-qemu-runner-action/compare/v1.5.0...v1.5.1) (2024-11-25)


### Bug Fixes

* **action:** Disk resizing ([#19](https://github.com/MattKobayashi/tailscale-qemu-runner-action/issues/19)) ([3eac2a2](https://github.com/MattKobayashi/tailscale-qemu-runner-action/commit/3eac2a2de56a8112e2fce35170f32eecab416cf8))

## [1.5.0](https://github.com/MattKobayashi/tailscale-qemu-runner-action/compare/v1.4.0...v1.5.0) (2024-11-25)


### Features

* **action:** Improve runner startup ([#16](https://github.com/MattKobayashi/tailscale-qemu-runner-action/issues/16)) ([56db248](https://github.com/MattKobayashi/tailscale-qemu-runner-action/commit/56db248a0765df1868b7a3a3fdc0b46a4b10a8e4))
* **action:** Use QEMU snapshot mode ([#17](https://github.com/MattKobayashi/tailscale-qemu-runner-action/issues/17)) ([2cce1a3](https://github.com/MattKobayashi/tailscale-qemu-runner-action/commit/2cce1a3dc12bab6208a8795c44fc01a8bdd8ab51))

## [1.4.0](https://github.com/MattKobayashi/tailscale-qemu-runner-action/compare/v1.3.1...v1.4.0) (2024-11-25)


### Features

* **action:** Enable nested virtualisation ([#14](https://github.com/MattKobayashi/tailscale-qemu-runner-action/issues/14)) ([c995be6](https://github.com/MattKobayashi/tailscale-qemu-runner-action/commit/c995be6a6cfd30cdae490721e4b64c496218aec5))

## [1.3.1](https://github.com/MattKobayashi/tailscale-qemu-runner-action/compare/v1.3.0...v1.3.1) (2024-11-25)


### Bug Fixes

* **action:** Add -enable-kvm flag ([#12](https://github.com/MattKobayashi/tailscale-qemu-runner-action/issues/12)) ([268ece4](https://github.com/MattKobayashi/tailscale-qemu-runner-action/commit/268ece45f21850875cc802458ca1e4ca22d1a6ef))

## [1.3.0](https://github.com/MattKobayashi/tailscale-qemu-runner-action/compare/v1.2.0...v1.3.0) (2024-11-24)


### Features

* **action:** Cleanup runner image files ([#10](https://github.com/MattKobayashi/tailscale-qemu-runner-action/issues/10)) ([648db1f](https://github.com/MattKobayashi/tailscale-qemu-runner-action/commit/648db1f92974d95dc0bd66b727500aceea1a03ff))
* **action:** Configurable runner labels ([#9](https://github.com/MattKobayashi/tailscale-qemu-runner-action/issues/9)) ([3024bbf](https://github.com/MattKobayashi/tailscale-qemu-runner-action/commit/3024bbf2da06178e9c7368ed859078cdd31dcd33))

## [1.2.0](https://github.com/MattKobayashi/tailscale-qemu-runner-action/compare/v1.1.0...v1.2.0) (2024-11-24)


### Features

* **action:** Make VM disk size configurable ([#6](https://github.com/MattKobayashi/tailscale-qemu-runner-action/issues/6)) ([282cedb](https://github.com/MattKobayashi/tailscale-qemu-runner-action/commit/282cedb818fbf8a91ec38f52bd5dcbc7cf11d2dd))

## [1.1.0](https://github.com/MattKobayashi/tailscale-qemu-runner-action/compare/v1.0.0...v1.1.0) (2024-11-24)


### Features

* **action:** Configurable APT mirror and timezone ([#3](https://github.com/MattKobayashi/tailscale-qemu-runner-action/issues/3)) ([a21a26e](https://github.com/MattKobayashi/tailscale-qemu-runner-action/commit/a21a26ec627f35f98ab371be3944ff639a861bdf))
* **action:** Improve runner shutdown ([#4](https://github.com/MattKobayashi/tailscale-qemu-runner-action/issues/4)) ([8664a60](https://github.com/MattKobayashi/tailscale-qemu-runner-action/commit/8664a60b2a055f1016a089bd517a7357032d3264))


### Bug Fixes

* **action:** Mask runner reg token ([bf8053c](https://github.com/MattKobayashi/tailscale-qemu-runner-action/commit/bf8053ce3ed05fe9781c626d2cd5d65b1d796ea1))
* **action:** Use correct dir for QEMU images ([d72a18c](https://github.com/MattKobayashi/tailscale-qemu-runner-action/commit/d72a18c842bd25bb65b25c20f6c92cc3b0235dcf))
* **action:** Use steps instead of needs ([98776f4](https://github.com/MattKobayashi/tailscale-qemu-runner-action/commit/98776f41e0ea22aa3112ce45cc499ec2277d6e6b))
* **action:** Use var instead of hardcoded URL ([7e084e6](https://github.com/MattKobayashi/tailscale-qemu-runner-action/commit/7e084e6a4fdafe55fdc211b1601ca4d2d40779fd))
* **README:** Fix example workflows ([d6bc05c](https://github.com/MattKobayashi/tailscale-qemu-runner-action/commit/d6bc05c095a228b4ed3b4c2249c6e6d486e19d4f))
* **README:** More example workflow fixes ([a742a1c](https://github.com/MattKobayashi/tailscale-qemu-runner-action/commit/a742a1ced43e8dc3d4c3bd456bd5c2682c240ff6))
