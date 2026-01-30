# nequip-gh-actions
Repository for shared nequip GitHub actions workflows

This repo contains a GitHub Actions reusable "Composite Action" to clone private repos. The workflow automatically checks out `main` or `develop` depending on what branch the tests are running on.

> [!IMPORTANT]  
> The secrets (like `NEQUIP_KEY`) must be Base64 encoded SSH private key files. In other words, if the file still starts with something like `-----BEGIN OPENSSH PRIVATE KEY-----` then you still need to encode it.
> You can Base64 encode on the command line on Mac [using OpenSSL](https://superuser.com/questions/120796/how-to-encode-base64-via-command-line-in-macos-os-x).

Note that the secrets have to be defined on the repo where the workflow is being called _from_.

# Setting up CI for new extension packages

1. Generate SSH keypair, e.g.
```
ssh-keygen -t ed25519 -C "gha-nequip-extension" -f nequip-extension-gha -N ""
```

2. Add public key to `nequip-private` through "Deploy keys"

3. Base64-encode private key
```
base64 -w 0 nequip-extension-gha
```

4. Add the base64-encoded private key as a GitHub Actions secret to the new extension package.
