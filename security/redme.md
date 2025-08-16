# SecureShip-CI Notes

- **Semgrep**: pulls `p/owasp-top-ten`, `p/security-audit`, and `p/secrets` from the registry. Override in workflow if needed.
- **Gitleaks**: uses `security/gitleaks.toml`. Add allowlist entries here to quell known false positives.
- **Trivy**: scans repo filesystem (deps + OS) and uploads SARIF. Fails on HIGH/CRITICAL by default.
- **ZAP Baseline**: set `ZAP_TARGET` at repo/org level (Repository → Settings → Variables → Actions). Job is skipped if unset.

Artifacts:
- SARIF for Semgrep/Gitleaks/Trivy in Security → Code scanning.
- `report.html` artifact for ZAP Baseline (download from workflow artifacts).

Tip: keep secrets out of repos; use GitHub Environments & Actions secrets.
