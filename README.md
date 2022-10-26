
## Comandos usuais no Git Flow

Este documnento foi criado com base no documento Git e Git Flow do Gitlab da Alterdata. Aque pode ser visualizado [aqui.](http://git-sqa.alterdata.matriz/bimer/docs/-/wikis/git-e-git-flow)


### Clonar o repositório criando uma pasta com o nome da tarefa
````
git clone http://172.16.101.7/bimer/web/on-premises/v1/wisepcp.git wpcp_9138
````
````
cd wpcp_9138
````
````
git flow init -d
````
````
git checkout develop
git pull
git branch

git flow feature start WPCP-9138
git branch
git pull
````


### Atualizar o branch develop e fazer um merge para o branch da tarefa
````
git checkout develop
git pull
git checkout minha_feature
git merge develop
````

### Finalizar a tarefa 
Caso ainda não tenha adicionado os arquivos novos e estiver executando em linha de comando (sem o Tortoise Git), execute u
````
git add . 
git commit -m ":emoji: <TAREFA> Mensagem"
````
O git add . é um coringa que adiciona todos os arquivos ainda não versionados. Se você quiser adicionar algum ou alguns arquivos específicos, use o nome do arquivo ou * na composição do nome. Ex: 'git add teste.txt', 'git add *.txt'.


🔥 ': fire :' - Para quando removemos código ou arquivos inteiros

🐛 ': bug :' - Para quando nosso commit corre um bug

✨ ': sparkles :' - Para quando nosso commit adiciona uma nova funcionalidade

````
git flow publish
````
Vá ao Gitlab para realizar o merge request
[Gitlab](http://git-sqa.alterdata.matriz/bimer/web/on-premises/v1/wisepcp/-/merge_requests)











### Criar um branch para Hotfix
Lembrando que o branch para hotfix irá, excepcionalmente, atualizar diretamente a main e que ao utilziar o git flow, o superset 'git flow finish' para finalizar o branch fará automaticamente um merge para develop.

#### Considerações: 
A pasta para a qual será realizada o clone (último parâmetro do git clone) deverá ter, idealmente, o número do processo criado para a liberação do hotfix; 

Deverá ter sido criada previamente no JIRA a versão especial, já que esse número será utilizado para criação do branch.

````
git clone http://172.16.101.7/bimer/web/on-premises/v1/wisepcp.git WPCP-XXXX 
````

````
cd WPCP-XXXX
````

````
git flow init -d
````

````
git checkout main
git pull
git flow hotfix start 1.X.45.X
````

Neste momento o branch estará pronto para receber as alterações. Utilize normalmente git add, git commit e, ao final git flow publish.

Quando a alteração estiver pronta utilize o 'git flow finsih'
````
git checkout hotfix/1.X.45.X
git flow hotfix finish 1.X.45.X -m “mensagem de liberação”
````


Após isso você será "jogado" para o branch develop. Agora execute os seguintes comandos na sequência:
````
git push
git checkout main
````

Em vias normais não deverá haver nada para subir
````
git push 
````

````
git push --tags
git checkout develop
````







