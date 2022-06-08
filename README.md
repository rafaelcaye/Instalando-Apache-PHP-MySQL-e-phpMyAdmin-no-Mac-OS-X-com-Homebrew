## Install Apache, PHP, MySQL and phpMyAdmin on Mac OS X with Homebrew


### 1) Install Homebrew: 

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```


### 2) Install VSCode:

```
brew install --cask visual-studio-code
```

Se você já tiver o Visual Studio Code instalado, poderá criar facilmente um `code` link simbólico com:

```
ln -s /Applications/Visual\ Studio\ Code.app/Contents/Resources/app/bin/code /opt/homebrew/bin/code
```
Depois disso será possível usar o Visual Studio Code para editar seus arquivos usando o `code` comando Terminal:

```
code filename
```

### 3) Enable Apache
```
sudo apachectl start
```

Test: http://localhost

---

### 4) Install PHP
```
brew install php
```
