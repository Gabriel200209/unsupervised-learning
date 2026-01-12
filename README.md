# Códigos da Disciplina

## Mini Tutorial de Git

Git é um sistema de controle de versão distribuído que permite rastrear mudanças no código. Aqui estão os comandos essenciais:

### Instalação
```bash
# No Ubuntu/Debian
sudo apt-get install git

# No macOS
brew install git

# No Windows
# Baixe de: https://git-scm.com/download/win
```

### Configuração Inicial
```bash
# Configurar nome de usuário
git config --global user.name "Seu Nome"

# Configurar email
git config --global user.email "seu.email@exemplo.com"

# Verificar configuração
git config --global --list
```

### Comandos Básicos

#### 1. **git clone** - Clonar um repositório
```bash
# Clonar um repositório remoto para sua máquina
git clone https://github.com/usuario/repositorio.git

# Clonar em uma pasta específica
git clone https://github.com/usuario/repositorio.git minha-pasta
```

#### 2. **git status** - Ver status do repositório
```bash
# Verificar arquivos modificados, staged e não rastreados
git status

# Versão resumida
git status -s
```

#### 3. **git add** - Adicionar arquivos ao staging
```bash
# Adicionar um arquivo específico
git add arquivo.txt

# Adicionar todos os arquivos modificados
git add .

# Adicionar todos os arquivos com extensão específica
git add *.py

# Adicionar arquivos de forma interativa
git add -p
```

#### 4. **git commit** - Criar um commit com as mudanças
```bash
# Commit com mensagem
git commit -m "Descrição das mudanças"

# Commit com mensagem mais detalhada
git commit -m "Título do commit" -m "Descrição detalhada das mudanças realizadas"

# Commit e adicionar automaticamente arquivos rastreados
git commit -am "Mensagem do commit"

# Alterar o último commit
git commit --amend -m "Nova mensagem"
```

#### 5. **git push** - Enviar commits para o repositório remoto
```bash
# Enviar commits para a branch atual
git push

# Enviar para um repositório remoto específico
git push origin main

# Enviar e criar branch remota
git push -u origin minha-branch

# Forçar push (cuidado!)
git push --force
```

#### 6. **git pull** - Atualizar com mudanças do repositório remoto
```bash
# Atualizar a branch atual
git pull

# Equivalente a:
# git fetch origin
# git merge origin/seu-branch
```

#### 7. **git fetch** - Buscar atualizações sem mesclar
```bash
# Buscar mudanças do repositório remoto
git fetch

# Buscar de um repositório específico
git fetch origin
```

### Trabalhando com Branches

#### Criar e mudar de branch
```bash
# Criar uma nova branch
git branch minha-branch

# Criar e mudar para a nova branch
git checkout -b minha-branch
# ou (Git 2.23+)
git switch -c minha-branch

# Listar todas as branches locais
git branch

# Listar todas as branches (local e remoto)
git branch -a

# Mudar para uma branch existente
git checkout minha-branch
# ou
git switch minha-branch

# Deletar uma branch local
git branch -d minha-branch

# Deletar uma branch remota
git push origin --delete minha-branch
```

### Histórico e Diffs

#### Ver histórico de commits
```bash
# Ver log de commits
git log

# Log em uma linha
git log --oneline

# Log com gráfico de branches
git log --graph --oneline --all

# Log com limite de commits
git log -n 5
```

#### Ver diferenças
```bash
# Ver mudanças não staged
git diff

# Ver mudanças staged
git diff --staged

# Ver diferenças entre branches
git diff main minha-branch

# Ver um arquivo específico
git diff arquivo.txt
```

### Desfazendo Mudanças

```bash
# Descartar mudanças em um arquivo
git checkout arquivo.txt
# ou
git restore arquivo.txt

# Descartar mudanças em todos os arquivos
git checkout .

# Remover arquivo do staging
git reset arquivo.txt

# Reset soft (mantém mudanças)
git reset --soft HEAD~1

# Reset hard (descarta tudo)
git reset --hard HEAD~1

# Reverter um commit específico
git revert <commit-hash>
```

### Exemplo de Fluxo Completo

```bash
# 1. Clonar repositório
git clone https://github.com/usuario/repositorio.git
cd repositorio

# 2. Criar uma branch para sua feature
git checkout -b minha-feature

# 3. Fazer mudanças nos arquivos...

# 4. Ver status
git status

# 5. Adicionar mudanças
git add .

# 6. Criar commit
git commit -m "Adiciona nova feature"

# 7. Atualizar com main (se necessário)
git pull origin main

# 8. Enviar para remoto
git push -u origin minha-feature

# 9. Criar Pull Request (no GitHub/GitLab)
# Depois de aprovado, fazer merge
```

### Dicas Úteis

- **Mensagens de commit**: Sejam descritivas e em tempo presente
- **Commit frequente**: Faça commits pequenos e lógicos
- **Pull antes de push**: Sempre atualize antes de enviar
- **Branches para features**: Use branches para cada feature/bugfix
- **Evite força**: Não use `git push --force` sem necessidade
- **Arquivo .gitignore**: Crie um arquivo para ignorar arquivos desnecessários

### Recursos Adicionais

- [Documentação oficial Git](https://git-scm.com/doc)
- [GitHub Docs](https://docs.github.com)
- [Guia Git em Português](https://rogerdudler.github.io/git-guide/index.pt_BR.html) 
