
## Comandos usuais no Git Flow


### Clonar o repositório criando uma pasta com o nome da tarefa
````
git clone http://172.16.101.7/bimer/web/on-premises/v1/wisepcp.git wpcp_9138
cd wpcp_9138
git checkout develop
git branch
git flow init
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