## What is the password less commands
## Ubuntu Instances
### Using Public Key
``` sh
ssh-copy-id -f "-o IdentityFile <PATH TO PEM FILE>" ubuntu@<INSTANCE-PUBLIC-IP>
```
- ssh-copy-id: This is the command used to copy your public key to a remote machine.
- -f: This flag forces the copying of keys, which can be useful if you have keys already set up and want to overwrite them.
- "-o IdentityFile ": This option specifies the identity file (private key) to use for the connection. The -o flag passes this option to the underlying ssh command.
- ubuntu@: This is the username (ubuntu) and the IP address of the remote server you want to access.
### Using passwords
- Go to the file # /etc/ssh/sshd_config.d/60-cloudimg-settings.conf
- Update # PasswordAuthentication yes
- Restart # SSH -> sudo systemctl restart ssh

## Ad_hoc commands to ping command
```sh
ansible -i <invetory file path> -m ping <host name or IP> like <web>
```
Once execute the passwords less authentication. we need to add the host name in invertory file on control node. then to check that connection use the above the ansible command.

