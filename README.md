## Install Apache, PHP, MySQL and phpMyAdmin on Mac OS X with Homebrew


### 1) Install Homebrew: 

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```


### 2) Install VSCode:

```
brew install --cask visual-studio-code
```

If you already have Visual Studio Code installed, you can easily create a code symlink with:

```
ln -s /Applications/Visual\ Studio\ Code.app/Contents/Resources/app/bin/code /opt/homebrew/bin/code
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
