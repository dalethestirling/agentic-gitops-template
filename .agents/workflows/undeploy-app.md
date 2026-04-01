---
description: Undeploy an application from the installed sync scope and move it to the uninstalled catalog.
---

# Undeploy Application Workflow

This workflow tracks the process of moving an application from the installed state to the uninstalled state, triggering ArgoCD to prune and remove the application from the cluster.

// turbo-all
1. **Validate File Exists:** Check that the application YAML file exists in the `installed/` directory.
2. **Move the File:** Move the application definition file from `installed/` to `uninstalled/`. (e.g., `mv installed/<app>.yaml uninstalled/`)
3. **Agent Action:** Validate that the application was properly defined in `catalog/` if necessary. (Generally undeployments just remove the reference).
4. **Git Commit:** Stage the changes, commit using the message `feat: undeploy <app>`, and push to the remote repository. (Note: push always requires user approval).
