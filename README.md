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
ln -s /Applications/Visual\ Studio\ Code.app/Contents/Resources/app/bin/code /opt/homebrew/bin/code
```
Depois disso será possível usar o Visual Studio Code para editar seus arquivos usando o `code filename` no Terminal.

_Obs.: O Visual Studio Code é o editor que eu prefiro. Você pode instalar outro editor se preferir._

----

### 1) Enable Apache

```
sudo apachectl start
```

Após executar o código acima, abra seu navegador e acesse http://localhost. Se for exibido **"It Works!"** estará configurado.



### 2) Install PHP

Com o comando abaixo será instalado a última versão do PHP.

```
brew install php
```
