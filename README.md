# Identity — Ben Leqeta

Cryptographic identity assertions and public keys for **Ben Leqeta** (`ben@loloma.group`).

This repository serves as a canonical reference for verifying my identity across platforms and tools.

---

## Contact

| | |
|---|---|
| **Email** | ben@loloma.group |
| **GitHub** | [@leqeta](https://github.com/leqeta) |
| **Organisation** | [Loloma Group International](https://loloma.group) |

---

## SSH Public Keys

Keys I use for authentication and signing. Also available at [github.com/leqeta.keys](https://github.com/leqeta.keys).

### Primary (ED25519)

```
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAICyae2p0joHuDOQAQfeV1dNQPq7UhacdXIl/dbGBiTqL ben@loloma.group
```

Used for: GitHub commits, git tag signing, SSH authentication.

### Git Signing (`allowed_signers`)

Machine-readable format for `gpg.ssh.allowedSignersFile` — see [`allowed_signers`](./allowed_signers).

---

## GPG

Primary GPG key fingerprint:

```
(run: gpg --keyserver keys.openpgp.org --search-keys ben@loloma.group)
```

---

## Keybase

Keybase proof: [keybase.io/leqeta](https://keybase.io/leqeta)

Keybase verifies this GitHub account is controlled by the same person as the Keybase identity.

---

## Platform Proofs

| Platform | Handle | Verified via |
|---|---|---|
| GitHub | [@leqeta](https://github.com/leqeta) | Keybase |
| Email | ben@loloma.group | Keybase |

---

## Verification

To verify a git commit or tag signed with my SSH key:

```bash
# 1. Fetch my signing keys
curl -fsL https://raw.githubusercontent.com/leqeta/identity/main/allowed_signers \
  > /tmp/leqeta_allowed_signers

# 2. Verify a commit
GIT_CONFIG_COUNT=1 \
GIT_CONFIG_KEY_0=gpg.ssh.allowedSignersFile \
GIT_CONFIG_VALUE_0=/tmp/leqeta_allowed_signers \
  git verify-commit <commit-sha>

# 3. Verify a tag
GIT_CONFIG_COUNT=1 \
GIT_CONFIG_KEY_0=gpg.ssh.allowedSignersFile \
GIT_CONFIG_VALUE_0=/tmp/leqeta_allowed_signers \
  git verify-tag <tag>
```

---

*Last updated: 2026-05-21*
