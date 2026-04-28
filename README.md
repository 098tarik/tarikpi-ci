# tarikpi-ci

GitHub Actions CI for Raspberry Pi automated updates.

## Setup

### 1. Install Tailscale on your Pi
```bash
curl -fsSL https://tailscale.com/install.sh | sh && sudo tailscale up
```

### 2. Generate SSH key on your Pi
```bash
ssh-keygen -t ed25519 -f ~/.ssh/github_actions -N ""
cat ~/.ssh/github_actions.pub >> ~/.ssh/authorized_keys
cat ~/.ssh/github_actions  # copy this private key
```

### 3. Add Secrets
Go to **Settings → Secrets and variables → Actions** and add:

| Secret | Value |
|--------|-------|
| `PI_SSH_KEY` | Private key from step 2 |
| `PI_HOST` | Pi's Tailscale IP or hostname |
| `PI_USER` | `browntarik` |

## Running
- Runs automatically **daily at 4 AM UTC**
- Trigger manually via **Actions → Update Raspberry Pi → Run workflow**
