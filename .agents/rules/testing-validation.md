---
trigger: always_on
---

# Testing & Validation
- **Linting Requirement**: No Helm chart change should be committed without passing `helm lint`.
- **Dry-run Validation**: For complex changes, use `helm template catalog/<app>` to verify the generated manifests before moving an app to `installed/`.
- **Workflow Integrity**: Always follow the sequence defined in `.agents/workflows/` (e.g., validate -> lint -> move -> commit).
