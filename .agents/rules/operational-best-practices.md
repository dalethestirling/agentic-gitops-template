---
trigger: always_on
---

# Operational Best Practices
- **Semantic Commits**: Use prefix-based commit messages (`feat:`, `fix:`, `docs:`, `chore:`) to maintain a clean history.
- **Directory Sovereignty**: Never mix application manifests in the wrong directory.
    - `catalog/`: Source of truth for Helm charts.
    - `uninstalled/`: Application manifests NOT currently synced by ArgoCD.
    - `installed/`: Application manifests synced by the root `application.yaml`.
