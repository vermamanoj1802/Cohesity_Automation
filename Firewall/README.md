# Firewall

**Do not edit any files under this subdirectory.**

This directory contains tools and configurations for managing firewall rules and integration with Cohesity automation. The resources here are intended for use as-is and should not be modified directly.

## Contents

- **firewallTool.py**: Python script for performing firewall operations.
- **firewall_tool_add_IP.yaml**: YAML configuration for adding IP addresses to the firewall.
- **firewall_tool_remove_IP.yaml**: YAML configuration for removing IP addresses from the firewall.
- **pyhesity.py**: Python library for Cohesity automation integration.

---

### General Guidelines

- **Do not edit files:** All scripts and configurations in this folder are maintained centrally. If you need changes, contact the repository maintainers.
- **Intended use:** These tools are designed to be used as part of automated workflows or by other scripts within this repository.

### How the Firewall Tools Work
The **add** and **remove** firewall tools are designed to work with an inventory file that contains server names. For each server:

1. The tool reads the server name from the inventory file.
2. It fetches the corresponding IP address from DNS.
3. It adds or removes the server's IP address from the Cohesity Network Firewall management rules.

**ℹ️This process ensures that firewall rules are dynamically managed according to the current server inventory, without requiring manual input of IP addresses.**

> **Warning:**  
⚠️These codes are provided on a best effort basis created for specific infra and is not in any way officially supported or sanctioned by Cohesity. The code in this repository are provided as-is and the author accepts no liability for damages resulting from its use.
