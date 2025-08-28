# Enviando arquivos daqui para VM

Comando para envio

        scp -i chaveprivada.key /caminho/local/arquivo.extensao ubuntu@IP.da.Máquina:/tmp/arquivo.extensao

Exemplo de envio de arquivo .ico

        scp -i chaveprivada.key /workspaces/code/favicon.ico ubuntu@129.146.56.151:/tmp/favicon.ico

Movendo arquivos para o docker

        docker cp /tmp/arquivo.extensao {nome do docker}:/usr/src/caminho/caminho_modules/@caminho/caminho/public/arquivo.extensao

Exemplo

        docker cp /tmp/favicon.ico mynodered:/usr/src/node-red/node_modules/@node-red/editor-client/public/favicon.ico

Depois reinicie o Docker

        docker restart >>nome do docker<<

Exemplo

        docker restart mynodered

Localizando arquivos
Buscando na VM completa

        find / -type f -name "*.ico" 2>/dev/null

Buscando na pasta terminal

        find ~/ -type f -name "*.ico"
