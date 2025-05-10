# 📘 Guia de Comandos Git — Versionamento de Código

## 🔧 Inicialização e Clonagem

| Comando                                       | Descrição                                             |
| --------------------------------------------- | ----------------------------------------------------- |
| `git init`                                    | Inicializa um novo repositório Git em uma pasta local |
| `git clone <URL>`                             | Clona um repositório remoto para sua máquina local    |
| `git clone --single-branch -b <branch> <URL>` | Clona apenas uma branch específica                    |

---

## 🧩 Configurações Globais

### 👤 Usuário

```bash
git config --global user.name "NOMEDEUSUARIO"
git config --global user.email "EMAIL"
```

### 🌿 Branch Padrão

```bash
git config init.defaultbranch                # Consulta o nome da branch padrão
git config --global init.defaultbranch main  # Define 'main' como padrão
```

### 🔐 Diretórios Seguros

```bash
sudo git config --global --add safe.directory /mnt/d
sudo git config --global --add safe.directory /mnt/d/*
```

### 🪪 Token GitHub

* Acesse: **GitHub > Settings > Developer Settings > Personal Access Tokens (classic)**
* Gere um novo token para clonar repositórios privados.

#### Armazenar o token para futuras autenticações:

```bash
git config --global credential.helper store
```

---

## 🔒 Autenticação com SSH

```bash
ssh-keygen -t ed25519 -C "seu_email@example.com"
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

---

## 🔍 Verificar Configurações

```bash
git config --global --list     # Configurações globais
git config --system --list     # Configurações do sistema
git config --local --list      # Configurações do repositório atual
```

---

## 📌 Gerenciamento de Repositórios

| Comando                    | Descrição                                         |
| -------------------------- | ------------------------------------------------- |
| `git status`               | Verifica o estado dos arquivos                    |
| `git add <arquivo>`        | Adiciona um arquivo específico                    |
| `git add .`                | Adiciona todos os arquivos modificados            |
| `git commit -m "mensagem"` | Salva as alterações com uma mensagem descritiva   |
| `git commit --amend`       | Altera o último commit (mensagem ou arquivos)     |
| `git log`                  | Mostra o histórico de commits                     |
| `git show`                 | Detalhes de um commit                             |
| `git diff`                 | Diferenças entre arquivos e último commit         |
| `git restore <arquivo>`    | Restaura alterações em um arquivo antes do commit |
| `git reset <arquivo>`      | Remove arquivo da staging area                    |

---

## 🌐 Repositório Remoto

| Comando                       | Descrição                                      |
| ----------------------------- | ---------------------------------------------- |
| `git remote -v`               | Lista os repositórios remotos                  |
| `git remote add origin <URL>` | Adiciona repositório remoto                    |
| `git push -u origin main`     | Envia commits para o repositório remoto        |
| `git pull`                    | Atualiza a branch local com alterações remotas |
| `git fetch`                   | Baixa dados do repositório remoto sem aplicar  |

---

### 🔀 Erro: "refusing to merge unrelated histories"

```bash
git pull origin main --allow-unrelated-histories
```

---

### 🔁 Alinhar Branch Local com o Remoto

```bash
git branch -m master main                      # Renomeia branch local
git branch -M main                             # Força renomeação (se já existir)
git branch --set-upstream-to=origin/main main # Seta rastreamento
```

---

## 🔁 Branches

| Comando                  | Descrição                        |
| ------------------------ | -------------------------------- |
| `git branch`             | Lista as branches locais         |
| `git branch <nome>`      | Cria uma nova branch             |
| `git checkout <branch>`  | Troca para outra branch          |
| `git checkout -b <nome>` | Cria e muda para a nova branch   |
| `git branch -d <nome>`   | Deleta uma branch local          |
| `git merge <branch>`     | Une branch especificada na atual |

---

## 📦 Stash (Alterações Temporárias)

| Comando           | Descrição                       |
| ----------------- | ------------------------------- |
| `git stash`       | Salva alterações não commitadas |
| `git stash list`  | Mostra as alterações salvas     |
| `git stash apply` | Restaura sem remover da lista   |
| `git stash pop`   | Restaura e remove da lista      |

---

## 🧹 Revertendo Mudanças

| Comando                      | Descrição                                      |
| ---------------------------- | ---------------------------------------------- |
| `git reset --soft <commit>`  | Volta ao commit, mantendo staging e arquivos   |
| `git reset --mixed <commit>` | Volta ao commit, limpa staging                 |
| `git reset --hard <commit>`  | Volta ao commit e descarta todas as alterações |
| `git checkout -- <arquivo>`  | Restaura arquivo do último commit              |
| `git restore <arquivo>`      | Forma moderna de restaurar arquivo             |
| `git revert <commit>`        | Cria novo commit que desfaz o anterior         |

---

## 🔂 Histórico de Commits e Recuperação

| Comando      | Descrição                                           |
| ------------ | --------------------------------------------------- |
| `git reflog` | Exibe histórico de referências (commits anteriores) |

---

## 📛 Convenções de Nomeclatura de Branches

* Use nomes curtos e descritivos.
* Padrões comuns:

  * `feature/login-api`
  * `bugfix/fix-logout-error`
  * `hotfix/security-patch`
  * `release/v1.0.0`
