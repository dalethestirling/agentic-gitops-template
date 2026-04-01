# agentic-gitops-template
Agentic GitOps Template for Kubernetes homelab management.

## Repository & Sync Architecture

This repository follows the "App of Apps" pattern for managing Kubernetes resources. The root [application.yaml](application.yaml) is the entry point for ArgoCD, which watches the `installed/` directory for application manifests.

- `catalog/`: Source of truth for Helm charts.
- `uninstalled/`: Application manifests that are not currently synced by ArgoCD.
- `installed/`: Application manifests that are synced by the root `application.yaml`.

## AI Agent Integration

This repository includes custom Agentic workflows and skills to streamline GitOps platform engineering operations. 

### Workflows
Located in `.agents/workflows/`, you can prompt an AI assistant to execute these standard routines:
- **`deploy-app`**: Moves a `catalog/` definition from `uninstalled/` to `installed/`, initiating an ArgoCD sync.
- **`undeploy-app`**: Removes an app from the `installed/` sync scope.
- **`scaffold-catalog-app`**: Bootstraps new helm charts into the repository matching homelab conventions.
- **`add-external-app`**: Create an ArgoCD application for an external Helm chart.

### Skills
Located in `.agents/skills/`, these provide context to your assistant during edits:
- **`app-yaml-validator`**: Ensures ArgoCD App manifests are correctly structured.
- **`helm-chart-standard-reviewer`**: Audits Helm templates during chart creation.
- **`version-checker`**: Checks for the existence of newer versions of container images and Helm charts.

### Rules
Detailed standards for configuration, testing, and operations are maintained in [.agents/rules/](.agents/rules/). All contributors and AI assistants must adhere to these rules.

## Catalog Applications

| Application | Status |
| ----------- | ------ |
| demoapp     | **Uninstalled** |

---

## Attribution & Usage

This project is a working example featured on [dalethestirling.github.io](https://dalethestirling.github.io/).

- **Author**: dalethestirling
- **Email**: [dale.stirling@gmail.com](mailto:dale.stirling@gmail.com)
- **License**: Licensed under the [Apache License, Version 2.0](LICENCE.md).

Feel free to use and adapt this code for your own projects. Attribution is appreciated!
