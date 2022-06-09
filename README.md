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
- Edit `ServerName www.example.com:8080`
- Edit `DocumentRoot` e `<Directory>`
- Set `AllowOverride All` (AllowOverride FileInfo AuthConfig Limit `AllowOverride none`)
- Enable `LoadModule rewrite_module lib/httpd/modules/mod_rewrite.so`
- Set `user` e `group`

Para iniciar/parar o servidor, execute os comandos abaixo no terminal:

```
sudo apachectl start
sudo apachectl stop
sudo apachectl restart
```

### 2) Install PHP

```
brew install php
```
