# vps-watch

Two scheduled GitHub Actions jobs, running on GitHub's servers (works even with the PC off):

- **oracle-a1-retry** — every 15 min, tries to create a free-tier Oracle A1.Flex instance in Tokyo (AD-1). Stops with a "failed" status (which triggers a GitHub email notification) on success or on an unexpected error.
- **xserver-vps-watch** — every 20 min, checks whether XServer's free VPS signup suspension notice is still on the page. Stops with a "failed" status (GitHub email notification) if the notice disappears.

Secrets required (Settings → Secrets and variables → Actions):
`OCI_CLI_USER`, `OCI_CLI_FINGERPRINT`, `OCI_CLI_TENANCY`, `OCI_CLI_REGION`, `OCI_CLI_KEY_CONTENT`, `OCI_SSH_PUBLIC_KEY`
