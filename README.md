# nequip-gh-actions-private
Repository for shared nequip GitHub actions workflows

This repo contains a GitHub Actions reusable "Composite Action" to clone private repos. The workflow automatically checks out `main` or `develop` depending on what branch the tests are running on.

> [!IMPORTANT]  
> The secrets (like `NEQUIP_KEY`) must be Base64 encoded SSH private key files. In other words, if the file still starts with something like `-----BEGIN OPENSSH PRIVATE KEY-----` then you still need to encode it.
> You can Base64 encode on the command line on Mac [using OpenSSL](https://superuser.com/questions/120796/how-to-encode-base64-via-command-line-in-macos-os-x).

Note that the secrets have to be defined on the repo where the workflow is being called _from_.