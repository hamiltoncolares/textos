# Ferramentas de apoio

## Tree

### Install

brew install tree

### Finalidade

Mostra a árvore do diretório no terminal

# Comandos de apoio

Instalar Homebrew

> $ ruby -e "$(curl -fsSL <https://raw.githubusercontent.com/Homebrew/install/master/install>)"

--------------------------------------------------------------------------------

## Virtual env

Instalar ferramentas

> $ pip install virtualenv $ pip install virtualenvwrapper

Criar diretório

> $ mkdir ~/.virtualenvs

Incluir diretório no bash ou zsh

> $ export WORKON_HOME=~/.virtualenvs source /usr/local/bin/virtualenvwrapper.sh

Criar virtualenv

> $ mkvirtualenv --python=/usr/local/bin/python3 myenv

--------------------------------------------------------------------------------

Iniciar projeto do Django

> $ django-admin startproject _nome do projeto_ .

Criar virtual env

> $ mkvirtualenv --python=/usr/local/bin/python3 _nome do virtual env_
