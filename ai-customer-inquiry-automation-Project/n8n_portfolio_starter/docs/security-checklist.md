# Public release security checklist

**Do not publish the raw workflow export without review.**

- [ ] No API keys, bearer tokens, passwords, OAuth tokens, webhook secrets, or authorization headers.
- [ ] No live webhook URLs, internal domains/IPs, database hosts, connection strings or callback URLs.
- [ ] No credential names or IDs identifying company accounts or individuals.
- [ ] No real customer names, email addresses, support-team addresses, or inquiry contents.
- [ ] No pinned execution data or copied logs with personal or confidential data.
- [ ] No sensitive values embedded in expressions, JavaScript/Code nodes, HTTP Request configuration, or AI prompts.
- [ ] No secrets in screenshots, image metadata, documentation, or sample data.
- [ ] Confirm permission to publish any work-related logic, designs, or brand references.
- [ ] Validate sanitized file imports into an isolated test workflow (do not run against production).
- [ ] Review every staged file before committing it to a public repository.

If a secret is accidentally committed, assume it is exposed and rotate/revoke it. Deleting the visible file does not erase Git history.
