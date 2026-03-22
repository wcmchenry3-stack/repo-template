# Project Name

> One-line description of what this project does.

## New Repo Setup Checklist

Complete these steps after creating from template, then delete this checklist.

### Repository
- [ ] Update this README with the actual project description
- [ ] Update `CLAUDE.md` with project-specific rules and architecture
- [ ] Update `docs/claude/architecture.md` with actual stack and design decisions
- [ ] Set repo visibility (public/private) in GitHub Settings

### CI/CD
- [ ] Open `.github/workflows/ci.yml` — uncomment the jobs relevant to your stack
- [ ] Set `working-directory` inputs if this is a monorepo (e.g., `backend/`, `frontend/`)
- [ ] Open `.github/workflows/deploy.yml` — fill in `service-id` and `zap-target-url` for each Render service
- [ ] Add GitHub Actions secrets in repo Settings → Secrets:
  - `RENDER_API_KEY` — Render API key (shared across all repos)
  - `SITE_URL` — live URL for ZAP weekly scan
  - `DATABASE_URL` — if project uses a database (for test jobs)

### Branch protection
After first CI run succeeds, add required status check names:
```bash
gh api --method PUT repos/wcmchenry3-stack/{repo}/branches/main/protection \
  --input - <<'EOF'
{
  "required_status_checks": {
    "strict": true,
    "contexts": ["secret-scan", "lint-python", "test-python", "cve-python"]
  },
  "enforce_admins": true,
  "required_pull_request_reviews": {"required_approving_review_count": 0, "dismiss_stale_reviews": true},
  "restrictions": null
}
EOF
```
Replace `contexts` with the actual job names from your `ci.yml`.

### First commit
```bash
git checkout -b feat/initial-setup
# make your changes
git add <specific files>
git commit -m "feat: initial project setup"
git push -u origin feat/initial-setup
gh pr create --draft --base main --title "feat: initial project setup"
```
