# 📘 Guia de Comandos Git — Versionamento de Código

## 🔧 Inicialização e Clonagem

Comando

Descrição

`git init`

Inicializa um novo repositório Git em uma pasta local

`git clone <URL>`

Clona um repositório remoto para sua máquina local

## 🧩 Configurações Globais

### 👤 Usuário

```bash
git config --global user.name "sidneylcarneiro"
git config --global user.email "sidneylcarneiro@yahoo.com"

```

### 🌿 Branch Padrão

```bash
git config init.defaultbranch            # Consulta o nome da branch padrão
git config --global init.defaultbranch main  # Define 'main' como padrão

```

### 🔐 Diretórios Seguros

```bash
sudo git config --global --add safe.directory /mnt/d
sudo git config --global --add safe.directory /mnt/d/*

```

### 🪪 Token GitHub

-   Acesse: **GitHub > Settings > Developer Settings > Personal Access Tokens (classic)**
    
-   Gere um novo token para clonar repositórios privados.
    

#### Armazenar o token para futuras autenticações:

```bash
git config --global credential.helper store

```

## 🔒 Autenticação

-   ✅ Pode ser feita com **token**, **chave SSH** ou **usuário e senha**
    
-   Para SSH:
    
    ```bash
    ssh-keygen -t ed25519 -C "seu_email@example.com"
    eval "$(ssh-agent -s)"
    ssh-add ~/.ssh/id_ed25519
    
    ```
    

## 🔍 Verificar Configurações

```bash
git config --global --list     # Lista todas as configurações globais
git config --system --list     # Lista configurações do sistema
git config --local --list      # Lista configurações do repositório atual

```

----------

## 📌 Gerenciamento de Repositórios

Comando

Descrição

`git status`

Verifica o estado dos arquivos no diretório

`git add <arquivo>`

Adiciona arquivos específicos para serem commitados

`git add .`

Adiciona **todos os arquivos modificados**

`git commit -m "mensagem"`

Registra um snapshot dos arquivos no histórico

`git log`

Mostra o histórico de commits

`git show`

Mostra os detalhes de um commit

`git diff`

Mostra as diferenças entre arquivos modificados e o último commit

----------

## 🌐 Conexão com Repositório Remoto

Comando

Descrição

`git remote -v`

Lista os repositórios remotos configurados

`git remote add origin <URL>`

Conecta o repositório local a um remoto

`git push -u origin main`

Envia os commits para o repositório remoto

`git pull`

Baixa as alterações do repositório remoto e atualiza local

`git fetch`

Baixa as alterações do repositório remoto sem aplicar

----------

## 🔁 Branches

Comando

Descrição

`git branch`

Lista branches locais

`git branch <nome>`

Cria nova branch

`git checkout <branch>`

Troca para a branch especificada

`git checkout -b <nome>`

Cria e muda para nova branch

`git merge <branch>`

Mescla uma branch na atual

`git branch -d <nome>`

Deleta uma branch local

----------

## 📦 Stash (Guardar alterações temporárias)

Comando

Descrição

`git stash`

Salva alterações não commitadas para voltar depois

`git stash apply`

Restaura alterações salvas

`git stash list`

Lista os stashes salvos

----------

## 🧹 Revertendo Mudanças

Comando

Descrição

`git reset --hard`

Remove todas as alterações locais não commitadas

`git checkout -- <arquivo>`

Restaura arquivo ao último commit

`git revert <commit>`

Cria um novo commit que desfaz outro
