# Security review, backups and operations

## Security review

- Inventory application routes, authentication, public endpoints, privileged operations, integrations and data boundaries.
- Run the project's build, type checks and relevant tests. Inspect dependency and secret-scan results with available tools. Review exploitable findings rather than blindly applying breaking upgrades.
- Check injection risks, XSS, CSRF where cookie-based mutation endpoints need it, unsafe redirects, SSRF, file uploads, path traversal, IDOR, privilege escalation and excessive data exposure.
- Validate all server inputs. Use parameterized queries, output-safe rendering, safe rich-text sanitization and upload MIME/size/type restrictions.
- Verify session/cookie settings, password reset behavior, role enforcement, RLS, Storage policies, webhook signatures, rate limits and abuse controls on sensitive endpoints.
- Review security headers and CSP against actual functionality. Avoid logging secrets, payment payloads or unnecessary personal data. Ensure production errors do not expose stack traces or credentials.
- Fix reproducible findings and rerun relevant tests and scans. Classify severity, affected component, evidence, remediation, retest result and residual risk. State scan tools and scope honestly.
- Restrict active probing to user-authorized systems and test environments. Avoid destructive tests, real charges and production load tests unless authorized.

## Backups and restoration

- Verify the chosen Supabase plan's actual database backup/PITR capabilities and retention using current official documentation. Never imply a paid capability is included by default.
- Cover database records, Storage object contents, migrations, source and configuration separately. A database backup alone does not prove uploaded product files are backed up.
- Choose recovery point and recovery time objectives with the client; propose reasonable options when unspecified. Define schedule, retention, encryption, access controls, location, cost and failure alerts.
- Keep backup credentials in secret management. Avoid storing backups in public buckets or source control.
- Restore a representative backup into an isolated environment when possible. Verify row counts, relationships, sample private assets and order/entitlement integrity. Record timing and evidence. Mark restoration as untested if blocked.
- Schedule jobs only through available authorized infrastructure. Verify job creation and a test execution; otherwise provide implementation and state the blocker.

## Maintenance and reporting

- Add useful error, payment webhook and fulfillment monitoring without unnecessary personal data. Document alerts and their actual configuration status.
- Prefer preview deployments and additive migrations. Back up before risky updates, validate compatibility and preserve an explicit rollback path.
- Report completed features, unfinished setup, tests run/passed/failed/blocked, security findings, backup/restore status and prioritized improvements.
- Distinguish observed metrics from AI inference. Support recommendations with evidence; never invent sales projections or compliance certification.
