# debian-vps-setup

setup script for my debian-based instances

## What it does

* Creates a new user and adds it to the `sudo` group.

* Disables login as `root`

* Disables password authentication

* Adds a public key to the new user's `authorized_keys`

## Usage

```bash
ssh root@<REMOTE HOST> \
  "curl -fsSL https://raw.githubusercontent.com/b-ggs/debian-vps-setup/master/setup | \
  USERNAME=boggs \
  HOST_PUBKEY=\""$(cat $HOME/.ssh/id_rsa.pub)"\" \
  /usr/bin/env bash"
```

**WARNING:** This script sets the new user's password to `p@ssw0rd` *(or the password you specify with the PASSWORD env var)*. **You should change this with `passwd` on your first login!**

### Environment Variables

* `USERNAME` *(required)* - The username of the nonroot user that will be created

* `HOST_PUBKEY` *(required)* - The public key to be added to the new user's `authorized_keys`

* `PASSWORD` - The password of the new user if you really don't care about security? *(default: `p@ssw0rd`)*

* `SSH_PORT` - Preferred port to access SSH through *(default: `22`)*

* `USER_SHELL` - Path to the new user's default shell *(default: `$(which bash)`)*

* `SSH_CONFIG_PATH` - Path to SSH config *(default: `/etc/ssh/sshd_config`)*
