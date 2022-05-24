# 06.1 - Atividade em Grupo

Nesta atividade vão criar um dynamoDB para suportar um jogo multiplayer. 

1. Abra seu Cloud9 e execute os seguintes comandos SEPARADAMENTE:
   ```shell
   pip3 install boto3
   cd ~/environment
   mkdir atividade-dynamodb && cd atividade-dynamodb
   curl -sL https://amazon-dynamodb-labs.com/static/game-player-data/battle-royale.tar | tar -xv
   ```
2. Para executar os comandos do tutorial sempre esteja na para `atividade-dynamodb` para garantir que esta na pasta certa execute o comando abaixo sempre que desejar.
   ```shell
    cd ~/environment/atividade-dynamodb
   ```
3. Caso tenha problemas com ler conteudo em inglês, recomendo que utilize o [plugin do google tradutor](https://chrome.google.com/webstore/detail/google-translate/aapbdbdomjkkjkaonfhkkikfgjllcleb?hl=pt) para seu maior conforto.
4. Agora execute o [Workshop: Modeling Game Player Data with Amazon DynamoDB](https://amazon-dynamodb-labs.com/game-player-data/plan-model.html) do passo 2: 'Plan your data model' até o 6: 'View past games'.
