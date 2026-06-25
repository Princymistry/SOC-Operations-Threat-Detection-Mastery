# Wazuh Agent Installation

## Windows 11 Agent

1. Opened Wazuh Dashboard.
2. Navigated to Agents > Deploy New Agent.
3. Selected Windows OS.
4. Specified Manager IP.
5. Copied and executed the installation command.
6. Verified that the agent status changed to Active.

## Kali Linux Agent

sudo apt install wazuh-agent

Edit:

sudo nano /var/ossec/etc/ossec.conf

Set Manager IP.

Restart service:

sudo systemctl restart wazuh-agent
