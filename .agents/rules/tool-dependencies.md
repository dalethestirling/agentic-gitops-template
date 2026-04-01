---
trigger: always_on
---

# Tool & Workflow Dependencies
- **Pre-execution Dependency Checks**: Before executing any workflow in `.agents/workflows/`, the assistant MUST verify the presence of the following tools:
    - `helm`: Required for linting and template generation.
    - `kubectl`: Required for cluster status checks.
    - `git`: Required for version control operations.
- **ArgoCD Context**: Ensure the assistant is aware of the `argoproj.io/v1alpha1` API version for all application manifests.
