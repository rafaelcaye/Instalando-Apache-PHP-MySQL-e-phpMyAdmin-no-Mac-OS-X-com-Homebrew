# Instalando Apache, PHP, MySQL e phpMyAdmin no Mac OS X com Homebrew

## Pré-requisito

### Install Homebrew

Abra o Terminal e execute o seguinte código:

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### Install Visual Studio Code

```
brew install --cask visual-studio-code
```

Definindo como padrão o comando `code` para edição de arquivos no Visual Studio Code:

```
ln -s /Applications/Visual\ Studio\ Code.app/Contents/Resources/app/bin/code /usr/local/homebrew/bin/code
```
----
### 1) Enable Apache

```
sudo apachectl start
```
Após executar o código acima, abra seu navegador e acesse http://localhost. Se exibir **"It Works!"** estará configurado.
##### Configure Apache
```
code /etc/apache2/httpd.conf
```
- Replace `Listen 8080` -> `Listen 80`
- Edit `ServerName`
- Edit `DocumentRoot` e `<Directory>`
- Enable `LoadModule rewrite_module lib/httpd/modules/mod_rewrite.so`
- Set `AllowOverride All` _(AllowOverride FileInfo AuthConfig Limit)_
- Set `user` e `group`

Para iniciar/parar o servidor, execute os comandos abaixo no terminal:

```
sudo apachectl start
sudo apachectl stop
sudo apachectl restart
```

### 2) Install PHP `brew install php`

#### Configure PHP

- Enable PHP in Apache `httpd.conf` and restart Apache: `LoadModule php_module /usr/local/opt/php/lib/httpd/modules/libphp.so`

```
<FilesMatch \.php$>
    SetHandler application/x-httpd-php
</FilesMatch>
```

- Include `index.php` -> `DirectoryIndex index.php index.html`

The php.ini and php-fpm.ini file can be found in: `/usr/local/etc/php/8.1/`

Restart PHP: `brew services restart php`
