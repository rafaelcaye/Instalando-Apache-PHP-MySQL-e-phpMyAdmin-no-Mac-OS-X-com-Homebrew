## Instalando Apache, PHP, MySQL e phpMyAdmin no Mac OS X com Homebrew



### Instale o Homebrew: 

Abra o Terminal e execute o seguinte código:

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```



### Instale o Visual Studio Code

```
brew install --cask visual-studio-code
```

Se você já tiver o Visual Studio Code instalado, poderá criar facilmente um `code` link simbólico com:

```
ln -s /Applications/Visual\ Studio\ Code.app/Contents/Resources/app/bin/code /opt/homebrew/bin/code
```
Depois disso será possível usar o Visual Studio Code para editar seus arquivos usando o `code filename` no Terminal.



### Habilite o Apache

```
sudo apachectl start
```

Após executar o código acima, abra seu navegador e acesse http://localhost. Se for exibido **"It Works!"** estará configurado.



### Instale o PHP
```
brew install php
```
