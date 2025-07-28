# Firebase Hosting

Instalando Firebase no CodeSpaces

Instale o Node.js

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

Crie uma pasta na raiz navegue até ela e instale o FireBase 

    npm install --unsafe-perm -g firebase-tools

Logando e deslogando no Terminal

    firebase login --no-localhost

Na página gerada de acessos ao seu Gmail na tela que confirma o comando clique em Next

Confirme a sessão ID depois Next

    12345

Copie o código de autorization como o abaixo e cole no bash

    4/0AVMBs.....NICYdDspx2DdAEsCKZAM3vcXxoPizgf4DHkgF9fmv1TBUHaHkyZNa....

Subindo site no Firebase
Iniciar Firebase

    firebase init hosting

No Json altere o pré-fixo do subdomínio:

    "site": ">>pré-fixo subdomínio<<",

Modelo Json para Dynamic Links

    {
    "hosting": {
    "site": ">>coloque aqui o subdomínio, removendo as setas<<",
    "public": "public",
    "ignore": [
      "firebase.json",
      "**/.*",
      "**/node_modules/**"
    ]
    },
    "functions": [
    {
      "source": "functions",
      "codebase": "default",
      "ignore": [
        "node_modules",
        ".git",
        "firebase-debug.log",
        "firebase-debug.*.log",
        "*.local"
      ],
      "predeploy": [
        "npm --prefix \"$RESOURCE_DIR\" run lint"
      ]
      }
    ]
    }

Subindo html no firebase
    
    firebase deploy --only hosting:pré-fixo subdomínio

Saindo do Firebase

    firebase logout

Removendo o Firebase

    npm uninstall -g firebase-tools

Verificando remoção

    firebase --version

