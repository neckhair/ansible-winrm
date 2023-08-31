# Update Windows remotely with Ansible

On Windows you need to activate WinRM first. Open a Powershell console as Administrator and run these commands:

```batch
WinRM quickconfig
```

Make sure the main network adapter has the "private" profile, not the "public" one. Otherwise the above command will fail. Got to Settings/Network to correct it.

Then run this playbook with the following command:

```sh
ansible-playbook -i hosts main.yaml
```

## Fixes

On MacOS I got an error when running the command. It can be fixed by exporting the `no_proxy` variable:

```sh
export no_proxy="*"
```
