---
trigger: always_on
---

# Configuration & Code Quality
- **Mandatory Skill Usage**: Any modification to ArgoCD Application manifests (in `installed/` or `uninstalled/`) MUST be validated using the `app-yaml-validator` skill.
- **Helm Chart Standards**: All new or modified Helm charts in `catalog/` MUST adhere to the `helm-chart-standard-reviewer` skill, specifically ensuring resource limits and ingress/route configurations are present.
- **Documentation Alignment**: Every new application added to the `catalog/` or moved to `installed/` must be reflected in the top-level `README.md` if it provides a core service.
