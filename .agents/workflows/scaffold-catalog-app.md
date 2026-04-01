---
description: Scaffold a new Helm chart application in the catalog and define its Application YAML in the uninstalled folder.
---

# Scaffold Catalog Application Workflow

This workflow guides the creation of a net-new application using the App of Apps GitOps pattern.

// turbo-all
1. **Create Catalog Scaffold:** Create a new directory in `catalog/<app>/` with minimal `Chart.yaml`, `values.yaml`, and `templates/` folder structure. (You can use `helm create catalog/<app>` if you prefer standard scaffolding, but remove unnecessary boilerplates).
2. **Scaffold Uninstalled App configuration:** Create a new file in `uninstalled/<app>.yaml` mapping to the new catalog path.
   - Remember to set `apiVersion: argoproj.io/v1alpha1`, `kind: Application`, `project: smart-home`, and source pointing to `catalog/<app>`.
3. **App Validation:** Trigger the `helm-chart-standard-reviewer` skill and `app-yaml-validator` skill to ensure your scaffolded resources match platform conventions.
4. **Git Commit:** Stage the changes, commit as `feat: scaffold <app>`.