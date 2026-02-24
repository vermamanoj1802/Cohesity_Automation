# Agent_Install

This directory contains Ansible playbooks for installing and configuring the Cohesity agent on Windows and Linux servers. Each playbook targets a specific use case.

| Playbook                | Purpose                                                                                                               | Workflow to Use |
|-------------------------|-----------------------------------------------------------------------------------------------------------------------|-----------------|
| `Windows_Server.yaml`   | Installs the Cohesity agent on a generic Windows Server. Handles basic installation and reboots the host if required. | Win_agent.yaml
| `Windows_SQL_Server.yaml` | Installs the Cohesity agent on a Windows Server running SQL Datbase. Also updates the Logon credentials for agent service and reboots if needed. | Win_SQL_agent.yaml |

## Playbook Details

### Windows_Server.yaml

- Installs the Cohesity agent on Windows Servers.
- Variables must be configured for your Cohesity Cluster connection.
- Enables Change block tracking for incremental backups ( reboot is required)
- Handles installation and triggers reboot if required.
- Requires the following variables:
  - `var_cohesity_server`: Cohesity Cluster address
  - `var_cohesity_admin`: Ansible username
  - `var_cohesity_password`: Ansible user password

### Windows_SQL_Server.yaml

- Installs the Cohesity agent on Windows Servers running SQL Server.
- Enables Change block tracking for incremental backups ( reboot is required)
- Sets new logon credentials for the Cohesity Agent service after installation.
- Triggers a reboot if the agent was installed/modified and reboot is enabled.
- Requires the following variables:
  - `var_cohesity_server`: Cohesity Cluster address
  - `var_cohesity_admin`: Ansible username
  - `var_cohesity_password`: Ansible user password
  - `logon user for Agent service`: sa-cohesity-mssql


> **Note:**  
> Customize variables as needed for your environment before running these playbooks.

> **Warning:**  
⚠️These codes are provided on a best effort basis created for specific infra and is not in any way officially supported or sanctioned by Cohesity. The code in this repository are provided as-is and the author accepts no liability for damages resulting from its use. 
