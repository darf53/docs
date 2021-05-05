# Installing a new mac

1. Setup SSH keys

2. Install Brew
    - [Install Brew](https://brew.sh)
    - $ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

3. Install Python3
    - [Install ptyhon3 on Mac](https://opensource.com/article/19/5/python-3-default-mac)
    - $ brew install pyenv
    - $ pyenv install 3.9.4
    - $ pyenv global 3.9.4
    - $ echo -e 'if command -v pyenv 1>/dev/null 2>&1; then\n  eval "$(pyenv init -)"\nfi' >> ~/.zshrc
    - Update .zshrc or .bashrc
```
    if command -v pyenv 1>/dev/null 2>&1; then
    eval "$(pyenv init -)"
    fi
```  

4. Install AWScli

```
