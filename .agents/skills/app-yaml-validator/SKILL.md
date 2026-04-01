---
name: app-yaml-validator
description: Validates that ArgoCD Application YAML files in installed/ or uninstalled/ meet the homelab requirements.
---

# App YAML Validator

When creating or modifying an ArgoCD `Application` YAML resource, ensure the following standards are met:

1. **API Version & Kind**: Must use `apiVersion: argoproj.io/v1alpha1` and `kind: Application`.
2. **Project**: The spec must define `project: smart-home`.
3. **Source Path**: The `spec.source.path` must correctly reference `catalog/<app-name>` where `<app-name>` is the name of the app.
4. **Source RepoURL**: The `spec.source.repoURL` must be set to `git@github.com:dalethestirling/homelab-gitops.git`.
5. **Destination**: Must have a valid destination namespace (usually matching the app name) and server set to `https://kubernetes.default.svc`.
6. **Sync Policy**: Must define automated sync (`prune: true`, `selfHeal: true`).

If any of these conditions are missing or incorrect, proactively fix them or alert the developer.
