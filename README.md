
## Comandos usuais no Git Flow


### Clonar o repositório criando uma pasta com o nome da tarefa
````
git clone http://172.16.101.7/bimer/web/on-premises/v1/wisepcp.git wpcp_9138
cd wpcp_9138
git flow init

git checkout develop
git pull
git branch

git flow feature start WPCP-9138
git branch
git pull
````


### Atualizar o branch develop e fazer um merge para o branch da tareda
````
git checkout develop
git pull
git checkout minha_feature
git merge develop
````

### Finalizar a tarefa 
Caso ainda não tenha adicionado os arquivos novos e estiver executando em linha de comando (sem o Tortoise Git), execute u
````
git add commit -m ":emoji: <TAREFA> Mensagem"
````

🔥 ': fire :' - Para quando removemos código ou arquivos inteiros

🐛 ': bug :' - Para quando nosso commit corre um bug

✨ ': sparkles :' - Para quando nosso commit adiciona uma nova funcionalidade

````
git flow publish
````

