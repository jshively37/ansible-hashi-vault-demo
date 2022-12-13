# Ansible and HashiCorp Vault

This is an example repo showing Ansible connecting to HashiCorp Vault to retrieve a username, password, and SNMP information stored in a simple K/V store.

The retrieve username and password is used to update SNMP on the device.


## Vault Config

For simplicity we are passing the Vault server and token using environment variables:
```
export VAULT_SERVER=''
export VAULT_TOKEN=''
```

Vault is configured with a simple KV store. The information is stored in Vault under a secret matching the `inventory_hostname`:

![images/vault_kv.png](images/vault_kv.png)


## Playbook Execution

Router state before:

![images/before_run.png](images/before_run.png)


Playbook Execution:

![images/playbook_run.png](images/playbook_run.png)


Router state after:

![images/after_run.png](images/after_run.png)
