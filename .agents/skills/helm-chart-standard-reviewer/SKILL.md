---
name: helm-chart-standard-reviewer
description: Validates that a Helm Chart within the catalog/ directory follows homelab standards.
---

# Helm Chart Standard Reviewer

When scaffolding, generating, or modifying a Helm Chart in the `catalog/` directory, verify that it adheres to standard homelab conventions:

1. **Ingress/Route Config**: Ensure the chart templates include a standard configuration for routing, ideally an HTTPRoute or an Ingress rule pointing to the right service.
2. **Resource Limits**: Check if pod templates (`Deployment`, `StatefulSet`, etc.) define minimum resource requests and limits.
3. **No Boilerplate Comments**: Remove any default Helm boilerplate comments from standard templates.
4. **Values Schema**: The `values.yaml` should be clean and clearly documented with only values that are actively overridden.
5. **Linting**: Before finalizing review, run `helm lint catalog/<app>` to verify the chart has no fatal parsing errors.

If finding any violations, proactively fix them or raise them as issues to fix before completing the task.
