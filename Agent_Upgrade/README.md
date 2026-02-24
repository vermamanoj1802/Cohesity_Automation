# Agent Upgrade

This directory contains files related to upgrading agents in the Cohesity KLB cluster.
| Playbook                | Purpose                                                                                                               | Workflow to Use |
|-------------------------|-----------------------------------------------------------------------------------------------------------------------|-----------------|
| `Win_agent_upgrade.yaml`   | Upgrade the Cohesity windows agent on server mentioned in Inventory/Agent file. | Agent_Upgrade_Windows.yml

## Files

### Win_agent_upgrade.yaml
This file contains the code to upgrade the Windows agents in the Cohesity cluster.

### pyhesity.py
This is a helper file used by `upgradeAgents.py`.

### upgradeAgents.py
This file is used by `Win_agent_upgrade.yaml` to run the upgrade command.

## Steps to Upgrade Windows Server

1. Edit the `Inventory/Agent` file.
2. Add the Windows server names to be upgraded under the section `[windows]`, for example:
    ```
    [windows]
    win-server1.company.com
    win-server2.company.com
    ```
3. Run the workflow `Agent_Upgrade_Windows.yml`.

> **Warning:**  
⚠️These codes are provided on a best effort basis created for specific infra and is not in any way officially supported or sanctioned by Cohesity. The code in this repository are provided as-is and the author accepts no liability for damages resulting from its use.
