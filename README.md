# ubuntu-vps-setup

setup script for my ubuntu-based instances

## Usage

This is to be run on the machine you want to give key-authenticated SSH access to.

**TL;DR**

```bash
ssh root@<REMOTE HOST> \
  "curl -fsSL https://raw.githubusercontent.com/b-ggs/ubuntu-vps-setup/master/setup | \
  /usr/bin/env bash -- <USERNAME> \
  <PASSWORD> \
  <YOUR MACHINE'S PUBLIC KEY>"
```

**Positional arguments**

\* - required

* `$1`* - The username of the nonroot user that will be created

* `$2`* - The password of the new user. Consider generating this with OpenSSL on your local machine

* `$3`* - The public key to be added to the new user's `authorized_keys`

* `$4` - Preferred port to access SSH through *(default: 22)*

* `$5` - Path to the new user's default shell *(default: `$(which bash)`)*

* `$6` - Path to SSH config *(default: `/etc/ssh/sshd_config`)*

**Example**

```bash
ssh root@<REMOTE HOST> \
  "curl -fsSL https://raw.githubusercontent.com/b-ggs/ubuntu-vps-setup/master/setup | \
  /usr/bin/env bash -- "boggs" \
  "password" \
  "$(cat $HOME/.ssh/id_rsa.pub)""
```

ssh hang-the-dj \
  "curl -fsSL https://raw.githubusercontent.com/b-ggs/ubuntu-vps-setup/master/setup | \
  /usr/bin/env bash -- "boggs" \
  "password" \
  "$(cat $HOME/.ssh/id_rsa.pub)""
