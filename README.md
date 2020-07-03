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

    
