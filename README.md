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
VERSION=cargo-deny@0ea3ced1541ae7a06487dbe723a95d809dbe964891fb5ec704227bd8e7fc33e0 # 0.18.1
```

## Link to the Renovate issue or Discussion

https://github.com/renovatebot/renovate/discussions/36182
