# Inventory

This directory contains inventory files that provide details about target servers and Windows/Linux parameters required by automation scripts in this repository. These files are referenced by Ansible playbooks and other scripts to determine which servers to act upon and what connection or configuration parameters to use.

## Purpose

- Define server hosts (Windows, workstations, etc.) for automation.
- Store connection and configuration parameters (such as credentials and connection types).
- Enable dynamic and secure management of infrastructure through Ansible.

## Usage

- Before running any automation scripts, update the relevant inventory file with the correct server and parameter details.
- Do not hard-code sensitive information; use environment variables or vaults as shown in examples.
  ```
  ansible_password={{lookup('env', 'ANSIBLE_WIN_PASSWORD')}}
- Scripts reference these inventory files via the `-i` flag or through configuration.

## Inventory File Mapping

| Inventory File     | Used With Script(s)                                                            |
|--------------------|--------------------------------------------------------------------------------|
| Agent              | - `Firewall/firewall_tool_add_IP.yaml`<br>- `Firewall/firewall_tool_remove_IP.yaml`<br>- `Agent_Install/Windows_Server.yaml`<br>- `Agent_Install/Windows_SQL_Server.yaml`<br>- `Agent_Register/win_register_API.yaml` |

> **Note:**  
> The above mapping is based on current repository usage. If you add new scripts or inventory files, please update this table.

> **Warning:**  
⚠️These codes are provided on a best effort basis created for specific infra and is not in any way officially supported or sanctioned by Cohesity. The code in this repository are provided as-is and the author accepts no liability for damages resulting from its use.
