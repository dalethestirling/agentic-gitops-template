---
trigger: always_on
---

# Maintain README.md
- The README.md should have a section containeing a table for each catalogue application.
- This table should:
    - Contain the application name
    - Contain the state of the application (installed/uninstalled)
- This should be updated when changes are made to file in the directory via the IDE
- Updates to this table should be made when running the following workflows: 
    - deploy-app
    - undeploy-app
- Updates to the table to add new catalog items should be done when a new application directory is added to the `catalog` directory
- Updates to the table to add new catalog items should be done when a new Application YAML is added to the `uninstalled` or `installed` directories
- Statuses for items  in the table will use one of the following statuses:
    - **Installed**: Used when a catalog item has a corresponding Application YAML file in the `installed`directory
    - **Uninstalled**: Used when a catalog item has a corresponding Application YAML file in the `uninstalled`directory
    - **Unknown**: Used when there is a directory in the catalog directory but no application YAML file