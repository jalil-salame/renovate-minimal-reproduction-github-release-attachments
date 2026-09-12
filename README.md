# 36182

## Current behavior

Currently renovate tries to update the [update string](#update-string) to the wrong digest (but the right version):

```ini
; Wrong digest
newDigest = 4dc89f5defcc1f86f1665ba1d9e03905926db4b6e550f7a1894a5280c874cf5d
newVersion = 0.18.2
```

The new digest is the digest of `cargo-deny-0.18.2-x86_64-unknown-linux-musl.tar.gz.sha256` (the checksum file), instead of the digest of `cargo-deny-0.18.2-x86_64-unknown-linux-musl.tar.gz` (the binary tarball).

## Expected behavior

Renovate should update the digest to the digest of the binary tarball:

```ini
; Correct digest
newDigest = 43c4a79c4b9fd1fcb3dddb305a1b4d8f7ac4a72accd61bb50a0b698789ca894c
newVersion = 0.18.2
```

## Update String

```sh
VERSION=cargo-deny@8ac46937040e08ea06fe0f87340c495b79c913cc86a36c065d7b9a8b352c14f3 # 0.20.2
```

## Link to the Renovate issue or Discussion

https://github.com/renovatebot/renovate/discussions/36182
