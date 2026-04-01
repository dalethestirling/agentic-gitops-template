---
description: Deploy an application from the uninstalled catalog into the installed sync scope.
---

# Deploy Application Workflow

This workflow tracks the process of moving an application from the uninstalled state to the installed state, meaning it will be deployed via ArgoCD across the cluster.

// turbo-all
1. **Validate File Exists:** Check that the application YAML file exists in the `uninstalled/` directory. (e.g., `ls uninstalled/<app>.yaml`)
2. **Lint the Chart:** Navigate to the application's Helm chart in `catalog/<app>/` and run `helm lint .` to ensure there are no syntax errors before deploying.
3. **Move the File:** Move the application definition file from `uninstalled/` to `installed/`. (e.g., `mv uninstalled/<app>.yaml installed/`)
4. **Agent Action - Review:** Check your `validate-workspace` and `app-yaml-validator` skills to verify the configuration properties of the moved application file.
5. **Git Commit:** Stage the changes, commit using the message `feat: deploy <app>`, and push to the remote repository. (Note: the push will require user approval).
