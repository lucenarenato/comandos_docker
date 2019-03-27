# Comandos basicos de docker

## Comandos Docker

### Linha de comando

## Sumário
### Listando
### Removendo
### Matando
### Alguns opções válidas de conhecer

- Lista todas as imagens da sua máquina inclusive as penduradas (dangling)

$ docker images -a

- Containers em execução
$ docker ps


- Todos containers
$ docker ps -a

- Apenas os IDs de todos os containers
$ docker ps -qa

- Removendo
$ docker rm ID
- Todos containers que foram parados
$ docker rm $(docker ps -qa)

- Uma imagem do sistema
- Se a imagem nao estiver em uso, você pode removê-la usando o comando abaixo e a ID da imagem
$ docker rmi ID

- Todas imagens do sistema
- Remove TODAS as imagens Docker que não estiverem em uso da sua máquina. Use com cuidado!

- Irá mostrar um erro caso alguma imagem esteja em uso.

$ docker rmi $(docker images -qa)

- Todas imagens do sistema
- Remove TODAS as imagens Docker que não estiverem em uso da sua máquina. Use com cuidado!

- Irá ignorar imagens em uso uso.

$ docker system prune --all

- resultado da remoção
- Matando
- Um ou mais containers
- Basta passar uma lista de IDs para matar mais do que um container

$ docker kill ID

- Alguns opções válidas de conhecer
 -a
- Maioria, se não todos, os comandos e subcomandos do Docker possuem uma opção -a que vem de all todos.

 –rm
- Mesma coisa coisa acontece com a opção --rm. Quando usada ela indica que o container deverá ser removido após sua execução

 -q
- Maioria, se não todos, os comandos e subcomandos do Docker possuem uma opção -q que lista apenas os IDs

## Outros comandos uteis

Segue a lista de comandos docker e sua utilidade:

sh
```
docker attach  – Acessar dentro do container e trabalhar a partir dele.
docker build   – A partir de instruções de um arquivo Dockerfile eu possa criar uma imagem.
docker commit  – Cria uma imagem a partir de um container.
docker cp      – Copia arquivos ou diretórios do container para o host.
docker create  – Cria um novo container.
docker diff    – Exibe as alterações feitas no filesystem do container.
docker events  – Exibe os eventos do container em tempo real.
docker exec    – Executa uma instrução dentro do container que está rodando sem precisar atachar nele.
docker export  – Exporta um container para um arquivo .tar.
docker history – Exibe o histórico de comandos que foram executados dentro do container.
docker images  – Lista as imagens disponíveis no host.
docker import  – Importa uma imagem .tar para o host.
docker info    – Exibe as informações sobre o host.
docker inspect – Exibe r o json com todas as configurações do container.
docker kill    – Da Poweroff no container.
docker load    – Carrega a imagem de um arquivo .tar.
docker login   – Registra ou faz o login em um servidor de registry.
docker logout  – Faz o logout de um servidor de registry.
docker logs    – Exibe os logs de um container.
docker port    – Abre uma porta do host e do container.
docker network – Gerenciamento das redes do Docker.
docker node    – Gerenciamento dos nodes do Docker Swarm.
docker pause   – Pausa o container.
docker port    – Lista as portas mapeadas de um container.
docker ps      – Lista todos os containers.
docker pull    – Faz o pull de uma imagem a partir de um servidor de registry.
docker push    – Faz o push de uma imagem a partir de um servidor de registry.
docker rename  – Renomeia um container existente.
docker restart – Restarta um container que está rodando ou parado.
docker rm      – Remove um ou mais containeres.
docker rmi     – Remove uma ou mais imagens.
docker run     – Executa um comando em um novo container.
docker save    – Salva a imagem em um arquivo .tar.
docker search  – Procura por uma imagem no Docker Hub.
docker service – Gernciamento dos serviços do Docker.
docker start   – Inicia um container que esteja parado.
docker stats   – Exibe informações de uso de CPU, memória e rede.
docker stop    – Para um container que esteja rodando.
docker swarm   – Clusterização das aplicações em uma orquestração de várias containers, aplicações junto.
docker tag     – Coloca tag em uma imagem para o repositorio.
docker top     – Exibe os processos rodando em um container.
docker unpause – Inicia um container que está em pause.
docker update  – Atualiza a configuração de um ou mais containers.
docker version – Exibe as versões de API, Client e Server do host.
docker volume  – Gerenciamento dos volumes no Docker.
docker wait    – Aguarda o retorno da execução de um container para iniciar esse container.
```
Obs.: É possível ver todos os comandos que o Docker possui, tendo o docker instalado, basta digitar no terminal docker --help


### Filtrando a lista de containers

docker ps -a -f status=exited
docker rm -v $(docker ps -a -q -f status=exited)

### Formatando a lista de containers
Por exemplo, o template:

"Oi meu nome é: {{.Name}}."

Então, pra começar cada uma das informações que aparecem na tela você pode chamar seguindo esse mapa:

CONTAINER ID: ID
IMAGE: Image
COMMAND: Command
CREATED: RunningFor
STATUS: Status
PORTS: Ports
NAMES: Names

Como eu geralmente só quero ver o nome, a imagem e o ID dos containers que estão rodando, meu comando acaba sendo esse:

docker ps -a --format "table {{.ID}}\t{{.Image}}\t{{.Names}}"



- http://renatolucena.net
- Renato Lucena - 2019 

