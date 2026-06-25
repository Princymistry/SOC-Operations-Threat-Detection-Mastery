# Useful Wazuh Queries

## Successful Logins

data.win.system.eventID:4624

## Failed Logins

data.win.system.eventID:4625

## SSH Failed Authentication

rule.groups:sshd

## Privilege Escalation

data.command:*sudo*

## Malware Detection

rule.description:*Trojan*
