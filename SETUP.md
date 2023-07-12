# Criar a pasta da aplicação.
Cria a pasta do Projeto como uma subpasta de **projeto**.

```
~/projeto
» mkdir vitest-template
» cd compras
vitest-tamplate on  master [?]
```
# Inicializar o GIT
Este comando inicia o controle de versão do código fonte em repositório local

```
~/projeto/vitest-template
» git init
```
# Inicializar o projeto
  Este comando cria um arquivo do projeto denominado **package.json** que
  controla as dependências das bibliotecas utilizadas no projeto.

```
~/projeto/vitest-template
» npm init -y
```
# Instalar biblioteca git-commit-msg-linter
Esta biblioteca é responsavel por padronizar as mensagens dos nossos commit. Segue o padrão do conventional commit, bloqueando commit que não estiverem em conformidade com este padrão.
 _"Conventional Commit"_.
  [Site conventional commit](https://www.conventionalcommits.org/en/v1.0.0/)

```
~/projeto/vitest-template
» npm i -D git-commit-msg-linter
```
# Cria arquivo .gitignore
Este arquivo serve para informamos as pastas / arquivos para os quais não desejamos controlar versão.

# Instalar o Typescript
Instala o compilador da linguagem de programação Typescript e os types do *node* que adicina tipagem ao mesmo, ajudando no intellisence dos comandos

```
~/projeto/vitest-template
» npm i -D typescript @types/node
```
# Inicializando projeto Typescript.
  Cria o arquivo de configuração do compilador typescript (tsconfig.json)
```
  ~/projeto/vitest-template
  » npx tsc --init
```
Como o typescript foi instalado como dependencia de desenvolvimento temos que utilizar o comando **npx** para executar o compilador **tsc**

## Arquivo de configuração do Typescript (tsconfig.json)

Este arquivo é inspecionado pelo typescript no momento da compilação
```
{
  "compilerOptions": {
    "incremental": true,
    "target": "es2022",
    "module": "CommonJS",
    "sourceMap": true,
    "removeComments": true,
    "esModuleInterop": true,
    "rootDirs": ["src","test"],
    "outDir": "./dist",
    "moduleResolution": "node",
    "strict": true,
    "skipLibCheck": true,
    "forceConsistentCasingInFileNames": true,
    "paths": {
      "@/*": ["*"],
      "@/test/*": ["../test/*"]
    },
    "baseUrl": "src"
  },
  "include": ["src", "test"]
}
```
# Instalando o ESLINT
Realiza a instalação do eslint, bem como configura o padrão da sintaxe do typescript tendo por base as regras definidas no style standard-with-typescript.
```
  ~/projeto/vitest-template
  » npm i --save-dev @typescript-eslint/parser @typescript-eslint/eslint-plugin eslint eslint-plugin-node

```
  ## Inicializando o eslint
  O eslint serve para pontuar erros de sintaxe e formatar o código fonte que estiver fora da especificação standard javascript style.
```
  ~/projeto/compras
  » npm init @eslint/config