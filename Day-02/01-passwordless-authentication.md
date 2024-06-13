# How to setup Passwordless Authentication

## EC2 Instances

### Using Public Key

```
ssh-copy-id -f "-o IdentityFile <PATH TO PEM FILE>" ubuntu@<INSTANCE-PUBLIC-IP>
```

- ssh-copy-id: This is the command used to copy your public key to a remote machine.
- -f: This flag forces the copying of keys, which can be useful if you have keys already set up and want to overwrite them.
- "-o IdentityFile <PATH TO PEM FILE>": This option specifies the identity file (private key) to use for the connection. The -o flag passes this option to the underlying ssh command.
- ubuntu@<INSTANCE-IP>: This is the username (ubuntu) and the IP address of the remote server you want to access.

### Using Password 

- Go to the file `sudo vim /etc/ssh/sshd_config.d/60-cloudimg-settings.conf`
- Update `PasswordAuthentication yes`
- Also goto sudo vim /etc/ssh/sshd_config
- uncomment 'PasswordAuthentication yes'
- Restart SSH -> `sudo systemctl restart ssh`
- create password now - sudo passwd ubuntu
- exit
- login again: ssh-copy-id ubuntu@ipaddr
- provide password
- again when we try to login - ssh ubuntu@ipaddr
- without authentication we can login now

# another way

- Goto Master server - ssh-keygen
- some files are generated now - ls /home/ubuntu/.ssh
- we can see priv and pub key
- cat /home/ubuntu/.ssh/id_rsa.pub
- we can see pub key now - copy it
- Goto Worker server - ssh-keygen
- again some files are generated here - ls ~/.ssh
- go inside authorized keys - vim ~/.ssh/authorised_keys
- paste pub key here.
- Lets ssh to target server now we can login inside it.

