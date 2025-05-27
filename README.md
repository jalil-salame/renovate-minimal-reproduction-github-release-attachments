# minimal-reproduction-template

First, read the [Renovate minimal reproduction instructions](https://github.com/renovatebot/renovate/blob/main/docs/development/minimal-reproductions.md).

Then replace the current `h1` with the Renovate Issue/Discussion number.

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
VERSION=cargo-deny@4dc89f5defcc1f86f1665ba1d9e03905926db4b6e550f7a1894a5280c874cf5d # 0.18.2
```

## Link to the Renovate issue or Discussion

Put your link to the Renovate issue or Discussion here.
