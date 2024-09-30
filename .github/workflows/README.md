# Automated build & deployment with Github Actions

This jekyll workflow triggers for every push on the default branch (master) consecutive actions on a remote server : 
- Clone repo & build jekyll website (into folder "_site")
- rename _site folder to www
- scp to ENS server (ssh key)

## Usage
To use it, you only have to setup the ssh connection properly.

### 1. Setup an ssh key
The ssh key must be **without** a passphrase. You can enter the following command, and then when asked for a passphrase & confirmation, tap *enter*.
"""
# rsa
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

# ed25519
ssh-keygen -t ed25519 -a 200 -C "your_email@example.com"
"""
Add the public key to the ENS server (add it to authorized_keys).

### 2. Store Secret variables
