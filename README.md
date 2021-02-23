# Comandos Docker

## Instalação
 * ##### Baixe as últimas atualizações do sistema
    * sudo apt update && sudo apt upgrade
 * ##### Para instalar o docker engine
    * sudo apt-get install apt-transport-https \
       ca-certificates \
       curl \
       gnupg-agent \
       software-properties-common
       
https://docs.docker.com/engine/install/ubuntu/

 * ##### Docker compose no GNU/Linux
    * sudo curl -L "https://github.com/docker/compose/releases/download/1.26.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

https://docs.docker.com/compose/install/



## Histórico de Lançamentos

* ##### Mostra as imagens existentes na máquina
    * docker images
* ##### Lista os containers em execução
    * docker ps
* ##### Mostra todos os containers, usando o complemento ‐a ao parâmetro ps é listado todos containers que já foram pausados ou fechados
    * docker ps -a
* ##### Ligar o container, pode receber como argumento o ID ou nome do container
    * docker start (id do container)
* ##### Desligar o container, pode receber como argumento o ID ou nome do container
    * docker stop (id do container)
* ##### Informa, em tempo de execução, detalhes sobre quanto o docker está consumindo de memória, cpu e etc.
    * docker stats
* ##### A imagem do nginx será baixada para o host, podendo ser aberto na porta 8080. Basta acessar no navegador o endereço: http://localhost:8080/
    * docker run -it -p 8080:80 nginx
    * Obs: O parâmetro ‐i possibilita termos interatividade com o container, e o ‐t que queremos nos linkar ao terminal do container. 
         Uso do ‐p informa que estamos informando ao Docker que a porta 8080 no host local será aberta e mapeada para a porta 80 no container
* ##### Com comando acima nosso console poderá ficar travado, com isso devemos executar o container em background, adicionando -d ao comando
    * docker run -it -d -p 8080:80 nginx
* ##### Com comando acima nosso console poderá ficar travado, com isso devemos executar o container em background, adicionando -d ao comando
    * docker run -it -d -p 8080:80 nginx
* ##### Destrói imagens, ao indicarmos o ID da imagem que queremos apagar
    * docker rmi IdContainer
* ##### Apaga todos os containers e imagens de uma só vez
    * docker rm $(docker ps ‐qa)
* ##### Apaga todos os containers e imagens de uma só vez
    * docker rmi $(docker images ‐q)

## Error deleting a Docker Image

* ##### You are not able to delete the Docker images
    * docker rmi 53d0b89b69b6
    * docker images purge
* ##### When you try to delete a Docker image, you face the following error messages:
    * Error response from daemon: conflict: unable to delete 53d0b89b69b6 (must be forced) - image is referenced in multiple repositories
    * Error response from daemon: conflict: unable to delete 53d0b89b69b6 (must be forced) - image is referenced in multiple repositories
    * Error response from daemon: conflict: unable to delete c9bc824b2e58 (cannot be forced) - image has dependent child images     
* ##### To solve this problem, you need to force the deletion of the docker image.
    * docker rmi 53d0b89b69b6 -f  
* ##### Here is the command output:
    * Deleted: sha256:53d0b89b69b69d2fefc89688da66a4fc4fdffe822217b5958627d5d30fa7eb2c
    * Deleted: sha256:66a479a7e7b749f39e613350e559bc62048f917592d88de2ceb8257517ed4894
    * Deleted: sha256:c9bc824b2e58c1ac340a04390468388cc2a4e9b8ddfaa4c7b8d3d3362e8360e4
    * Deleted: sha256:785ba2cb224274c2396b0f08f9c9b1bec632451141407b5e6dbb9c77e4acb555
* ##### The following command will delete all Docker images.
    * docker rmi $(docker images -a -q) -f
