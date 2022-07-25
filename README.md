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
### 1) Install Apache
```
brew install httpd
```
Access in your browser: http://localhost. If show **"It Works!"**, all ok!

#### Configure Apache

```
code /usr/local/etc/httpd/httpd.conf
```

- Replace `Listen 8080` -> `Listen 80`
- Edit `ServerName`
- Edit `DocumentRoot` and `<Directory>`
- Enable `LoadModule rewrite_module lib/httpd/modules/mod_rewrite.so`
- Set `AllowOverride All` _(AllowOverride FileInfo AuthConfig Limit)_
- Set `user` and `group`

Start/stop/restart Apache commands:

```
brew services start httpd
brew services stop httpd
brew services restart httpd
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

### 3) Install MySQL
```
brew install mysql
``` 

Restart MySQL: `brew services restart mysql`

### 4) Install phpMyAdmin

```
brew install phpmyadmin
```

Enable phpMyAdmin in Apache to open with `http://localhost/phpmyadmin`
```
    Alias /phpmyadmin /opt/homebrew/share/phpmyadmin
    
    <Directory /opt/homebrew/share/phpmyadmin/>
        Options Indexes FollowSymLinks MultiViews
        AllowOverride All
        <IfModule mod_authz_core.c>
            Require all granted
        </IfModule>
        <IfModule !mod_authz_core.c>
            Order allow,deny
            Allow from all
        </IfModule>
    </Directory>
```
