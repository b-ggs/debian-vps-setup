# ubuntu-vps-setup

setup script for my ubuntu-based instances

## Usage

On your local machine:

```bash
ssh root@<REMOTE_HOST> \
  "USERNAME="<YOUR VPS USER>" \
  PASSWORD="<PASSWORD>" \
  SSH_PORT="<PREFERRED SSH PORT>" \
  HOST_PUBKEY="<YOUR PUBKEY>";" + \
  '$(curl -fsSL https://raw.githubusercontent.com/b-ggs/ubuntu-vps-setup/master/setup)'
```

Example:

```bash
ssh root@xxx.xx.xx.xx \
  "USERNAME="deploy" \
  PASSWORD="password" \
  SSH_PORT="22" \
  HOST_PUBKEY="$(cat $HOME/.ssh/id_rsa.pub)";" + \
  '$(curl -fsSL https://raw.githubusercontent.com/b-ggs/ubuntu-vps-setup/master/setup)'
```
