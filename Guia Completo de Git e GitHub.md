# 📘 Guia Completo de Git e GitHub para Iniciantes

![Git e GitHub]

## 📋 Índice
- [Prefácio](#prefácio)
- [Legenda de Ícones](#legenda-de-ícones)
- [1. Configuração Inicial](#1-configuração-inicial-️)
- [2. Controle de Versão Local](#2-controle-de-versão-local-)
- [3. Integração com GitHub](#3-integração-com-github-)
- [4. Trabalho Colaborativo](#4-trabalho-colaborativo-)
- [5. Gerenciamento Avançado](#5-gerenciamento-avançado-)
- [6. Segurança e Boas Práticas](#6-segurança-e-boas-práticas-)
- [7. Comandos Úteis](#7-comandos-úteis-️)
- [8. Recursos de Aprendizado](#8-recursos-de-aprendizado-)
- [9. Pull Requests e Code Reviews](#9-pull-requests-e-code-reviews-)
- [10. GitHub Actions e CI/CD](#10-github-actions-e-cicd-)
- [11. Git para Projetos Markdown](#11-git-para-projetos-markdown-)
- [12. Deploy de Dashboards do Power BI](#12-deploy-de-dashboards-do-power-bi-com-github-e-fabric-)

## 📝 Prefácio
Este guia foi criado para ajudar iniciantes a dominar o Git e GitHub, com foco especial em analistas de dados e profissionais de BI. Você aprenderá desde os conceitos básicos até técnicas avançadas de colaboração e integração com ferramentas de análise de dados.

## 🔣 Legenda de Ícones
| Ícone | Significado | Ícone | Significado |
|-------|-------------|-------|-------------|
| 📦 | Commit | 🌿 | Branch |
| 🔄 | Sincronização | 🔀 | Merge |
| 🔍 | Revisão | ⚙️ | Configuração |
| 💾 | Armazenamento | 🚀 | Deploy |
| 📊 | Análise de Dados | 👥 | Colaboração |
| 🔒 | Segurança | 🛠️ | Ferramentas |
| ⚠️ | Alerta | ✅ | Confirmação |
| ❌ | Proibição | 📝 | Documentação |
| 🧪 | Testes | 🔧 | Manutenção |

---

## 1. Configuração Inicial ⚙️

> *Primeiros passos para configurar o Git em seu ambiente*

### 1.1 Instalação do Git 💻

```bash
# Windows/Mac: https://git-scm.com/downloads
# Linux (Debian/Ubuntu):
sudo apt-get update && sudo apt-get install git

# Verificar instalação: ✅
git --version
```

### 1.2 Configuração Básica 🔧

git config --global user.name "Seu Nome"
git config --global user.email "seu.email@provedor.com"

# Configurar editor padrão (VSCode exemplo): 📝
git config --global core.editor "code --wait"

## 2. Controle de Versão Local 💾
### 2.1 Iniciar Repositório 🏗️

mkdir meu-projeto && cd meu-projeto
git init
echo "# Meu Projeto" >> README.md

### 2.2 Ciclo Básico de Trabalho 🔄

# Verificar status: 🔍
git status

# Adicionar arquivos: ➕
git add arquivo.sql
git add .          # Todos os arquivos
git add *.sql      # Todos .sql

# Commitar: 📦
git commit -m "Descrição clara das alterações"

# Ver histórico: 📜
git log --oneline --graph --decorate

## 3. Integração com GitHub 🌐
### 3.1 Conectar Repositórios 🔗
# Criar repositório no GitHub primeiro
git remote add origin https://github.com/seu-user/meu-projeto.git
git branch -M main
git push -u origin main

### 3.2 Enviar Atualizações 📤

# Fluxo padrão: 🔁
git add .
git commit -m "Melhoria na estrutura do banco"
git push

## 4. Trabalho Colaborativo 👥
### 4.1 Clonar Projeto 📋

git clone https://github.com/usuario/repositorio.git
cd repositorio

### 4.2 Atualizar Localmente 📥

git pull origin main

# Equivalente a: 🔄
git fetch origin
git merge origin/main

### 4.3 Branching Strategy 🌿

# Nova feature: 🆕
git checkout -b feature/nova-funcao

# Publicar branch: 📤
git push -u origin feature/nova-funcao

# Merge após aprovação: 🔀
git checkout main
git merge feature/nova-funcao

## 5. Gerenciamento Avançado 🔧
### 5.1 .gitignore 🙈

# Exemplo para projeto SQL:
*.bak
*.log
.env
/dados/
config.ini

### 5.2 Desfazer Ações ↩️

| Situação | Comando | Exemplo |
|----------|---------|---------|
| Modificação não commitada ❌ | git checkout -- arquivo | git checkout -- relatorio.md |
| Alterar último commit 🔄 | git commit --amend | git commit --amend -m "Mensagem corrigida" |
| Reset suave (mantém alterações) 🔙 | git reset --soft HEAD~1 | git reset --soft HEAD~1 |
| Reset completo (descarta alterações) ⚠️ | git reset --hard HEAD~1 | git reset --hard HEAD~1 |
| Reverter commit específico 🔄 | git revert commit_id | git revert a7d3f1c |
| Desfazer adição ao staging 🔙 | git restore --staged arquivo | git restore --staged dashboard.pbix |
| Descartar todas as mudanças locais ⚠️ | git reset --hard | git reset --hard |
| Remover arquivos não rastreados 🧹 | git clean -fd | git clean -fd |
| Recuperar commit após reset hard 🔄 | git reflog + git checkout | git reflog; git checkout HEAD@{1} |

### 5.3 Resolver Conflitos ⚔️➡️🤝
Execute git pull e encontre arquivos com <<<<<<< HEAD

Edite manualmente para resolver diferenças ✏️

Finalize com: ✅

git add arquivo-resolvido.sql
git commit -m "Resolve conflito de merge"

## 6. Segurança e Boas Práticas 🔒
✅ Faça: 👍

📦 Commits pequenos e frequentes

📝 Mensagens descritivas

📥 Pull antes de trabalhar

🌿 Use branches para novas features

❌ Evite: 👎

🔑 Commitar dados sensíveis

📜 Alterar histórico público

🚫 Trabalhar direto na main

⚠️ Push forçado (-f)

## 7. Comandos Úteis 🛠️

# Ver diferenças não commitadas 👁️
git diff

# Listar branches remotas 🌿
git branch -a

# Salvar trabalho temporário 💼
git stash
git stash pop

# Ver configurações ⚙️
git config --list

## 8. Recursos de Aprendizado 📚
Documentação Oficial do Git 📖

https://git-scm.com/doc

## 9. Pull Requests e Code Reviews 🔍
### 9.1 Criar Pull Request 📤

# No GitHub: 🌐
# 1. Navegue até o repositório 🏠
# 2. Clique em "Pull requests" > "New pull request" ➕
# 3. Selecione a branch de origem e destino 🔀
# 4. Clique em "Create pull request" ✅
# 5. Adicione título e descrição detalhada 📝

### 9.2 Revisar Pull Request 👀

# Boas práticas para code review: 🔎
# - Verifique a funcionalidade ✅
# - Avalie a qualidade do código 📊
# - Teste em seu ambiente local: 🧪
git fetch origin
git checkout pull/ID/head

### 9.3 Merge de Pull Request 🔀

# Via GitHub UI ou terminal: 💻
git checkout main
git merge --no-ff feature/nova-funcao
git push origin main

## 10. GitHub Actions e CI/CD 🚀
### 10.1 Configuração Básica ⚙️

# Crie arquivo .github/workflows/ci.yml: 📄
# name: CI
# 
# on:
#   push:
#     branches: [ main ]
#   pull_request:
#     branches: [ main ]
# 
# jobs:
#   build:
#     runs-on: ubuntu-latest
#     steps:
#     - uses: actions/checkout@v2
#     - name: Run tests
#       run: |
#         echo "Executando testes..."
#         # comandos de teste

### 10.2 Automações Úteis 🤖

# - Testes automatizados 🧪
# - Linting e verificação de código 🔍
# - Deploy automático 🚀
# - Notificações de build 🔔

## 11. Git para Projetos Markdown 📝
### 11.1 Visualização de Diferenças 👁️

# Comparar versões de documentos: 📄
git diff HEAD~1 documento.md

### 11.2 Colaboração em Documentação para Times de Analistas de Dados 📊👥

# Estrutura de repositório recomendada: 📂
# /analises           # Notebooks e scripts de análise 📊
# /dados              # Metadados e amostras (não dados sensíveis) 📈
# /docs               # Documentação do projeto 📚
# /relatorios         # Relatórios e visualizações 📋
# /queries            # Consultas SQL e scripts de ETL 💾
# /modelos            # Modelos estatísticos ou de ML 🧠

# Fluxo de trabalho para times de dados: 👥
# 1. Crie um repositório centralizado: 🏢
git init projeto-analytics
cd projeto-analytics
git remote add origin https://github.com/sua-empresa/projeto-analytics.git

# 2. Configure branches de proteção: 🔒
# No GitHub: Settings > Branches > Add rule
# - Proteja a branch 'main' 🛡️
# - Exija revisões de pull request 👀
# - Exija testes de CI passarem ✅

# 3. Convide membros da equipe: 👥
# No GitHub: Settings > Collaborators > Add people
# Atribua funções: Admin, Write, Read 🔑

# 4. Estabeleça convenções de documentação: 📏
# - README.md na raiz com visão geral do projeto 🏠
# - CONTRIBUTING.md com guias de contribuição 🤝
# - Documentação técnica em /docs 📚
# - Comentários em código seguindo padrões (docstrings) 💬

# 5. Compartilhe análises via Jupyter Notebooks: 📓
# - Use nbconvert para exportar para Markdown 🔄
jupyter nbconvert --to markdown analise.ipynb
git add analise.md
git commit -m "Adiciona análise exploratória de dados de vendas"

# 6. Colaboração em tempo real: ⏱️
# - Use GitHub Codespaces para ambiente compartilhado 💻
# - Ou JupyterHub para notebooks colaborativos 📊
# - Vincule ao GitHub via extensões 🔌

# 7. Revisão de código e análises: 🔍
# - Crie pull requests para revisão de pares 👥
# - Use comentários inline para feedback específico 💬
# - Utilize ferramentas como nbdime para diff de notebooks: 📊
nbdime compare old_notebook.ipynb new_notebook.ipynb

# 8. Integração com ferramentas de BI: 📊
# - Vincule documentos ao Power BI/Tableau via URLs 🔗
# - Documente fontes de dados e transformações 📝
# - Mantenha dicionário de dados atualizado 📖

# 9. Automação de documentação: 🤖
# - Configure GitHub Actions para gerar docs: ⚙️
# .github/workflows/docs.yml para executar Sphinx/MkDocs
# - Publique automaticamente no GitHub Pages 🌐

# 10. Gestão de conhecimento: 🧠
# - Use GitHub Wiki para documentação colaborativa 📚
# - Mantenha um registro de decisões (ADRs) 📝
# - Crie templates para issues e PRs específicos para análises 📋

# Sugestões para trabalho em equipe: 👥
# - Use uma branch por análise ou feature 🌿
# - Mantenha parágrafos em linhas separadas para facilitar merge 📄
# - Utilize issues para discutir metodologias e abordagens 💬
# - Padronize nomenclatura de arquivos e variáveis 📏
# - Documente pressupostos e limitações das análises 📝
# - Implemente revisões técnicas antes de publicar resultados 🔍

# Exemplo de fluxo para nova análise: 📊
git checkout -b analise/comportamento-cliente
# Trabalhe nos notebooks e scripts 📓
git add .
git commit -m "Adiciona análise de segmentação de clientes"
git push origin analise/comportamento-cliente
# Crie PR no GitHub e solicite revisão da equipe 👀👥

### 11.3 Boas Práticas para Pull Requests em Projetos de Análise de Dados 📊🔎

# Estrutura recomendada para descrição do PR: 📝
# - Contexto da análise 🔍
# - Metodologia utilizada 🧪
# - Principais descobertas 💡
# - Impacto nos KPIs de negócio 📈
# - Próximos passos sugeridos 🔮

# Exemplo de descrição de PR: 📋
# ```
# ## Análise de Churn de Clientes 📉
# 
# **Contexto:** Investigação dos fatores que levam ao cancelamento de assinaturas 🔍
# 
# **Metodologia:** 🧪
# - Análise exploratória em Python/R 📊
# - Modelagem com Random Forest 🌲
# - Validação cruzada com 5-fold ✅
# 
# **Descobertas:** 💡
# - Clientes com mais de 6 meses têm 30% menos chance de churn 📉
# - Problemas de suporte aumentam churn em 2.5x ⚠️
# - Identificados 3 segmentos de alto risco 🎯
# 
# **Impacto:** 💼
# - Potencial redução de 15% no churn mensal 📈
# - ROI estimado de 3.2x para ações de retenção 💰
# 
# **Próximos passos:** 🔮
# - Implementar score de propensão ao churn 📊
# - Testar campanhas de retenção para segmento de alto risco 🎯
# ```

# Processo de revisão técnica: 🔍
# 1. Revisor verifica a metodologia: 🧪
git checkout pull/42/head
# Examine notebooks e scripts 📓

# 2. Validação de resultados: ✅
# - Reproduzir análises críticas 🔄
# - Verificar cálculos de métricas
# - Testar com subconjuntos de dados

# 3. Feedback construtivo:
# - Use comentários específicos no GitHub
# - Sugira melhorias na visualização
# - Questione pressupostos quando necessário
# - Proponha análises complementares

# 4. Aprovação e merge:
# - Exija pelo menos 2 aprovações para análises críticas
# - Documente decisões importantes nos comentários
# - Após aprovação, faça o merge:
git checkout main
git merge --no-ff analise/comportamento-cliente
git push origin main

# 11.4 Documentação Pós-Análise

# Após o merge, atualize a documentação:
# 1. Adicione a análise ao índice de conhecimento
# 2. Atualize o README com novas descobertas
# 3. Crie ou atualize dashboards relacionados
# 4. Vincule a análise a issues resolvidas

# Exemplo de atualização de documentação:
git checkout -b docs/atualiza-analise-churn
# Edite arquivos de documentação
git add docs/analises/churn.md
git commit -m "Documenta metodologia e resultados da análise de churn"
git push origin docs/atualiza-analise-churn
# Crie um novo PR para a documentação

# 11.5 Compartilhamento de Resultados

# Opções para compartilhar com stakeholders:
# - GitHub Pages para relatórios públicos
# - Wiki interna para documentação técnica
# - Integração com ferramentas de BI
# - Apresentações geradas a partir de notebooks

# Exemplo de publicação via GitHub Pages:
# Configure em Settings > Pages
# Selecione branch e pasta (/docs)
# URL: https://sua-empresa.github.io/projeto-analytics/

# Automação de publicação:
# Crie .github/workflows/pages.yml:
# ```yaml
# name: Deploy Pages
# on:
#   push:
#     branches: [ main ]
#     paths: [ 'docs/**' ]
# jobs:
#   build-and-deploy:
#     runs-on: ubuntu-latest
#     steps:
#       - uses: actions/checkout@v2
#       - name: Setup Python
#         uses: actions/setup-python@v2
#         with:
#           python-version: '3.x'
#       - name: Install dependencies
#         run: |
#           python -m pip install --upgrade pip
#           pip install jupyter nbconvert mkdocs
#       - name: Convert notebooks
#         run: |
#           jupyter nbconvert --to markdown docs/notebooks/*.ipynb
#       - name: Deploy
#         uses: JamesIves/github-pages-deploy-action@4.1.4
#         with:
#           branch: gh-pages
#           folder: docs
# ```

# 11.6 Manutenção Contínua do Repositório

# Práticas recomendadas:
# - Revisão trimestral de análises antigas
# - Arquivamento de análises obsoletas
# - Atualização de dependências
# - Limpeza de branches mescladas

# Comandos para manutenção:
# Listar branches mescladas:
git branch --merged main

# Remover branches locais mescladas:
git branch --merged main | grep -v "^\*" | xargs git branch -d

# Atualizar dependências (exemplo com Python):
pip freeze > requirements.txt
git add requirements.txt
git commit -m "Atualiza dependências do projeto"
git push origin main

---

# 12. Comandos uteis

 **Para visualizar diretórios remotos no GitHub**

`Cod`: git remote -v 

**Realiza criação de nova branch.**

`Cod`: git checkout -b 'Nome da Branch'

**Realiza a movimentação entre branch**

`Cod`: git checkout 'Nome da Branch'

**Para identificar em qual branch estou**

`Cod`: git branch

**Para Mesclar novas funcionalidades**

`Cod`: git merge 'Nome da Branch'

**Para renomear branch**

`Cod`: git branch -m 'Nome da Branch' 'branchrenomeada'

**Para deletar branch**

`Cod`: git branch -d 'Nome da Branch' 

**Comando stash caixa temporarias**

`Cod`: git stash save 'Nome da Branch' 

**Comando stash list**

`Cod`: git stash list

**Comando stash pop para tirar da caixa**

`Cod`: git stash pop [1]

**Comando stash clear para descartar da caixa**

`Cod`: git stash clear

**Para ver Logs**

`Cod`: git log  
`Cod`: git log 'nomedapasta'
`Cod`: git log 'nomedoarquivo'
`Cod`: git log --oneline
`Cod`: git log --graph
`Cod`: gitk

**Como reveter commits** Cuidado

`Cod`:  git revert 654das65

**Retorna/restoura para STAGING/INDEX**

`Cod`:  git reset --soft HEARD1~1

**Retorna/restoura para WORKING DIR**

`Cod`:  git reset --mixed HEAD^1

**Remove objeto**

`Cod`:  git reset --hard HEAD^1

**Para reverter o commit**
`Cod`:  git revert 654das65

**tag anotada inclui informações extras como autor, data e mensagem
`Cod`: git tag -a v1.0.0 -m "Primeiro lançamento"

**Ver todas as tags do repositório:

`Cod`:  git tag

 **Ver detalhes de uma tag anotada:

 `Cod`: git show nome-da-tag

  **Enviar as tags para o GitHub (após criá-las):

  `Cod`: git push origin nome-da-tag

**Ou, para enviar todas as tags de uma vez:
`Cod`: git push origin --tags

**Excluir uma tag localmente:
 `Cod`: git tag -d v1.0.0

 ** Excluir uma tag do GitHub (remota):
  `Cod`: git push origin --delete v1.0.0

** Criar uma tag em um commit específico:
 `Cod`: git tag v1.0.0 123abc456def
















## 👤 Autor

**Élmesson de Jesus**

**Formação:**
- Graduação: Gestão da Tecnologia da Informação
- Pós-Graduação: Business Intelligence e Analytics

**Ano:** 2025

---

## 📚 Fontes de Pesquisa

Este guia foi elaborado com base nas seguintes fontes:

1. **Documentação Oficial do Git**
   - https://git-scm.com/doc
   - https://git-scm.com/book/en/v2

2. **GitHub Docs**
   - https://docs.github.com/pt/get-started
   - https://docs.github.com/pt/actions

3. **Atlassian Git Tutorial**
   - https://www.atlassian.com/git/tutorials

4. **Pro Git Book** por Scott Chacon e Ben Straub
   - https://git-scm.com/book/en/v2

5. **GitHub Learning Lab**
   - https://lab.github.com/

6. **Melhores Práticas para Equipes de Dados**
   - https://github.blog/2020-05-20-using-github-for-data-science-collaboration/
   - https://neptune.ai/blog/git-for-data-science-projects

7. **Integração com Ferramentas de BI**
   - https://docs.microsoft.com/en-us/power-bi/create-reports/desktop-git-integration
   - https://docs.microsoft.com/en-us/fabric/cicd/git-integration/intro-to-git-integration

8. **Jupyter e Git**
   - https://jupyterlab.readthedocs.io/en/stable/user/git.html
   - https://github.com/jupyterlab/jupyterlab-git

9. **Visualizer para praticar**
   - https://git-school.github.io/visualizing-git/
