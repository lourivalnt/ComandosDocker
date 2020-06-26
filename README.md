# Comandos Docker

## Instalação
 * ##### Baixe as últimas atualizações do sistema.
    * sudo apt update && sudo apt upgrade
    * sudo apt-get install apt-transport-https \
       ca-certificates \
       curl \
       gnupg-agent \
       software-properties-common

https://docs.docker.com/engine/install/ubuntu/

## Histórico de Lançamentos

* ##### Mostra as imagens existentes na máquina
    * docker images
* ##### Lista os containers em execução
    * docker ps
* ##### Mostra todos os containers, usando o complemento ‐a ao parâmetro ps é listado todos containers que já foram pausados ou fechados
    * docker ps -a
* ##### Outra opção bastante utilizada é a ‐q, que retorna apenas o ID do container
    * docker ps ‐qa
* ##### Informa, em tempo de execução, detalhes sobre quanto o docker está consumindo de memória, cpu e etc.
    * docker stats

    
