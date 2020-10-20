SSH
===============================
#macOS

- Keys are by default located at ~/.ssh/
- It is my personal practice to have multiple public auth keys, one for each remote origin. This way if my private key pair is compromised, not all other remote origins will be at risk, and I can easily revoke a key pair if needed.

### Generate an SSH Key
- RSA SSH key
	- RSA keys are usually 2048 or 4096 bits (param `-b`), on my machine (macOS) the default is 3072.
	- Default RSA signature type is rsa-sha2-512
```
ssh-keygen -t rsa -b 2048 -C “email@hostname” -f ~/.ssh/[private-key]
```
- ed25519 SSH key
	- ed25519 is the most recommended public key algorithm to date
```
ssh-keygen -t ed25519 -C “email@hostname” -f ~/.ssh/[private-key]
```

### SSH Config
- Update SSH config
	-	This lets you have different keys for different sites
```
Host ssh.dev.azure.com
User me
StrictHostKeyChecking yes
IdentityFile ~/.ssh/id_azuredevops_rsa
IdentitiesOnly yes
```

#### Add an SSH Key to the ssh-agent and KeyChain
- This will put it in "Keychain Access.app" prefixed with `SSH:`
```
ssh-add -K ~/.ssh/[private-key]
```

### Read an SSH Key
- Check an ssh key on your machine against a known fingerprint
	-	By default the base64 encoded `sha-256` fingerprint is shown, but sometimes you want to view the hexadecimal `md5` fingerprint instead
	-	`-l` lists the fingerprint hash for the input file
	-	`-f` provides the input file argument
	-	`-E` changes the fingerprint hash to md5 instead of the default sha-256
```
ssh-keygen -l -f ~/.ssh/id_rsa.pub                  # sha-256 fingerprint
ssh-keygen -l -E sha256 -f ~/.ssh/id_rsa.pub
ssh-keygen -l -E md5 -f ~/.ssh/id_rsa.pub
```
- This also works with checking the fingerprints of certs in `known_hosts`
```
ssh-keygen -l -f ~/.ssh/known_hosts
```




