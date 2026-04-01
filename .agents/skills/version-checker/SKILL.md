---
name: version-checker
description: Checks for the existence of newer versions of container images and Helm charts referenced in the repository.
---

# Version Checker Skill

Use this skill to scan for and report on available updates for container images and Helm charts used in the GitOps environment.

## Execution Steps

1. **Scan Resources**: 
   - Parse YAML files in `installed/`, `uninstalled/`, and `catalog/`.
   - Identify container image tags (e.g., `repository:tag` or `image: some/repo:tag`).
   - Identify Helm chart versions for external applications in `uninstalled/`.

2. **Filter criteria**:
   - **Ignore `latest`**: If an image tag is `latest`, do not check for updates.
   - **Focus on SemVer**: Prioritize semantic versioning for comparison.

3. **Check for Updates**:
   - **Helm Charts**: Use `helm repo update` followed by `helm search repo <chart> --versions` to find the latest version.
   - **Container Images**: Use `search_web` or query registry manifests (if tools available) to find newer stable tags for the identified repository.

4. **Reporting**:
   - Present a table of identified updates.
   - Include: Application Name, Current Version, Newest Version, and Source (Registry/Repo).

## Standard Constraints
- Do not suggest beta or RC versions unless the current version is also a beta/RC.
- Ensure the `app-yaml-validator` is run after any manual version bump.
