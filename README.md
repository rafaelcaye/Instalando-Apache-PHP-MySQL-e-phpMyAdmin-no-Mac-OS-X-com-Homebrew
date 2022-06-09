# Instalando Apache, PHP, MySQL e phpMyAdmin no Mac OS X com Homebrew

## Pré-requisito

### Install Homebrew

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### Install Visual Studio Code

```
brew install --cask visual-studio-code
```

Sets `code` as the default command for editing files in Visual Studio Code:

```
ln -s /Applications/Visual\ Studio\ Code.app/Contents/Resources/app/bin/code /usr/local/homebrew/bin/code
```
----
### 1) Enable Apache
```
sudo apachectl start
```
Access in your browser: http://localhost. If show **"It Works!"**, all ok!

#### Configure Apache

```
code /etc/apache2/httpd.conf
```

- Replace `Listen 8080` -> `Listen 80`
- Edit `ServerName`
- Edit `DocumentRoot` and `<Directory>`
- Enable `LoadModule rewrite_module lib/httpd/modules/mod_rewrite.so`
- Set `AllowOverride All` _(AllowOverride FileInfo AuthConfig Limit)_
- Set `user` and `group`


Start/stop/restart Apache commands:

```
sudo apachectl start
sudo apachectl stop
sudo apachectl restart
```

### 2) Install PHP
```
brew install php
``` 

#### Configure PHP

1. Enable PHP in Apache `httpd.conf`: 
```
LoadModule php_module /usr/local/opt/php/lib/httpd/modules/libphp.so

<FilesMatch \.php$>
    SetHandler application/x-httpd-php
</FilesMatch>
```

2. Include `index.php` -> `DirectoryIndex index.php index.html`

3. Restart PHP: `brew services restart php`
