# MQTT no docker Oracle Cloud

1. Instalação do Docker

        sudo apt-get update

- 

        sudo apt-get install ca-certificates curl gnupg lsb-release

-

        curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

-

        echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \

-

        $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

Se já tiver inslado não irá funcionar no Oracle Cloud

        sudo apt-get update

Se já tiver inslado não irá funcionar no Oracle Cloud

        sudo apt-get install docker-ce docker-ce-cli containerd.io

Adicione seu usuário ao docker

        sudo usermod -aG docker $USER

2. Instalação do Container Eclipse - Mosquitto

Crie as pastas:

        sudo mkdir -p /mosquitto/config


        
        sudo mkdir /mosquitto/data


        
        sudo mkdir /mosquitto/log

Edita o mosquitto.conf

        sudo nano /mosquitto/config/mosquitto.conf

Conteúdo mosquitto.conf

          persistence true
          persistence_location /mosquitto/data/ 
          log_dest file /mosquitto/log/mosquitto.log 
          allow_anonymous true
          listener 1883

#Ctrl + O para salvar

#Ctrl + X para sair

3. Execução do Container

        docker run -d -p 1883:1883 -p 9001:9001 -v /mosquitto:/mosquitto eclipse-mosquitto

Tutorial´para AWS https://www.youtube.com/watch?v=z5vx93uKr_U
