# Code

Abrindo VM Oracle Cloud

Pré requisito: Acesse como Administrador

    sudo su -

Login no Servidor

    ssh -i chaveprivada.key ubuntu@>>IP da Máquina Virtual<<
    
# Instalando Node Red

Pré requisito: Acesse como Administrador

    sudo su -

Atualize o sistema

    sudo apt update

Instale o curl

    sudo apt install curl

Adicione o repositório do Node.js (versão 20 LTS):

    curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -

Instale o Node.js

    sudo apt install nodejs

Verifique as versões do node e npm

    node -v
    npm -v

Atualize o npm

    npm install -g npm@11.4.2

Instale o docker

    sudo apt update && sudo apt install docker.io -y

Verifique versões do docker

    docker --version

Instale o Node Red

    docker run -it -p 1880:1880 -v node_red_data:/data --name noderedxp nodered/node-red

Implementando bloqueio de fluxo controle fluxos Node Red

Pré requisito: Acesse como Administrador

    sudo su -

Descubra o nome do container:

    docker ps

Acesse seu container

    docker exec -it >nome do container< bash

Exemplo

    docker exec -it mynodered bash

Instale o modulo dentro do container

    npm install bcryptjs

Crie sua senha criptografada

    node -e "console.log(require('bcryptjs').hashSync('>Sua senha<', 8))"

Exemplo
    
    node -e "console.log(require('bcryptjs').hashSync('umasenhaqualquer', 8))"

Vai gerar a chave criptografada como abaixo

    $2b$08$ACLA3/..KiUmOqsNPLY0sOR4PU995TrE/O4zalzcdEnLo8lW/inWG.

Agora navegue até as linhas de settings e mude conforme necessidade.


Navegue até settings

    cd /data
    nano settings.js

Navegar para fora do Container

    exit

Reeniciem o docker

    docker stop >>nome do container<<
    docker start >>nome do container<<

Apagando Container NodeRed

Parar o container

    docker stop >>nome do container<<

Remover o container

    docker rm >>nome do container<<

Remover a imagem do Node-RED

    docker rmi nodered/node-red

Remover volume de dados

    docker volume rm node_red_data

Verificar se tudo foi removido

    docker ps -a
    docker images
    docker volume ls
