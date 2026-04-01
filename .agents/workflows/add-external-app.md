---
description: Create an ArgoCD application for an external Helm chart and add it to the uninstalled directory.
---

# Add External Helm Application Workflow

This workflow guides the creation of a new ArgoCD application that points to an external Helm repository.

// turbo-all
1. **Source Collection:** Ask the user for the following information if not already provided:
   - Application Name
   - Helm Repository URL
   - Chart Name
   - Chart Version
   - Target Namespace
2. **Validation:** Verify the Helm chart is accessible using `helm show chart --repo <repo_url> <chart_name> --version <version>`.
3. **Scaffold Uninstalled App configuration:** Create a new file in `uninstalled/<app>.yaml`.
   - Use `apiVersion: argoproj.io/v1alpha1`, `kind: Application`.
   - Set `spec.source` to use the provided Helm repository, chart, and version.
   - Set `spec.destination.namespace` to the target namespace.
4. **Update README:** Add the new application to the `Catalog Applications` table in `README.md` with a status of **Uninstalled**.
5. **Validation:** Trigger the `app-yaml-validator` skill to ensure the manifest matches platform conventions.
6. **Git Commit:** Stage the changes, commit as `feat: add external app <app>`.
