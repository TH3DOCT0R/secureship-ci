# SecureShip CI — Secure SDLC Pipeline Template
**Stack:** GitHub Actions, Semgrep, Gitleaks, Trivy, OWASP ZAP Baseline

Drop-in CI that runs code secrets scan, dependency/containers scan, and a ZAP baseline. Outputs JUnit/HTML/SARIF artifacts and gates merges on fail.

## Usage
- Copy `.github/workflows/secure-ci.yml` into your repo
- Optional: add `semgrep.yml`, `gitleaks.toml`, `zap-baseline.conf`

Artifacts appear in the workflow run and as SARIF (for code scanning).
