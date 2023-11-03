# public

Public repository for hosting files

Install everything a developer needs to get started on Mac

```
# install brew
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### `.zshrc`

Requires node.js install from website.

```
alias l='ls -laGFh'
alias ll='ls -laGFh'
alias wttr='curl http://wttr.in/<your lat/lng>'

ssh-add --apple-use-keychain ~/.ssh/<rsa_token>

alias devd='ssh developer-machine@1.2.3.4'

git-whoami () {
    git config --global user.name
    git config --global user.email
}

git-<username> () {
    git config --global commit.gpgsign false
    git config --global --unset user.signingkey
    git config --global user.name "<name>"
    git config --global user.email "<email>"
}

setup () {
    # setup npm to not require sudo
    mkdir -p "${HOME}/.npm-packages"
    npm config set prefix ~/.npm-packages
    sudo chown -R 504:20 "/Users/$USER/.npm"
    
    # setup xcode tooling - required to use basic developer tooling
    xcode-select --install
}

update () {
    brew install gh
    brew install awscli
    brew install gdal
    brew install wget
    brew install make
    brew install cmake
    brew install jq
    brew install minio/stable/mc
    brew install python3
    brew install nmap

    brew install syncthing
    brew services start syncthing

    brew install youtube-dl
    brew install ffmpeg

    brew install --cask citrix-workspace
    brew install --cask amazon-workdocs-drive
    brew install --cask rocket-chat
    brew install --cask webstorm
    brew install --cask pycharm
    brew install --cask datagrip
    brew install --cask microsoft-remote-desktop
    brew install --cask hdfview
    brew install --cask drawio

    curl https://bootstrap.pypa.io/get-pip.py | python3
    pip install rasterio
    
    docker run -d -p 8000:8000 -p 9000:9000 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce
    
    sudo npm i -g http-server
    npm i -g pm2
}
```
