# Projeto Lista de Tarefas com Docker

Esse projeto foi elaborado durante o Módulo de __Back-end__ do curso da Trybe para desenvolver habilidades com os conteúdos e tecnologias de: <br>
<br>
🔹 Conteinerizar aplicações;<br>
🔹 Criar uma conexão entre elas;<br>
🔹 Orquestrar seu funcionamento. <br>

 ###### :warning: Importante <br> <br> Apenas os arquivos indicados nos requisitos foram desenvolvidos pelo(s) aluno(s), os demais são de autoria da Trybe.

## Índice
- [Elaboração](#elaboração)
- [Sobre](#sobre)
- [Estrutura do Projeto](#estrutura-do-projeto)
- [Instalação](#instalação)
- [Testes](#testes)
   - [Cobertura de Testes](#cobertura-de-testes)
- [Status](#status)
- [Requisitos](#requisitos)
   - [Requisitos Obrigatórios](#requisitos-obrigatórios)
   - [Requisitos Bônus](#requisitos-bônus)


## Elaboração
<a href="https://github.com/aimemartins">
  <img src="https://avatars.githubusercontent.com/u/108954069?v=4" width="80px" alt="Aimê Martins"/> <p>Aimê Martins</p>


## Sobre

Temos uma aplicação full-stack neste repositório: um aplicativo de tarefas! Esta aplicação precisa ser conteinerizada para funcionar. Você deverá desenvolver os arquivos de configuração para cada frente específica: __Front-end__, __Back-end__ e, no nosso caso, para um aplicativo de __teste__ que valida se as aplicações estão se comunicando. <br>

Você deverá criar as imagens para as aplicações e configurar essas imagens com o `docker-compose`. <br>

Para isto, você irá utilizar uma série de comandos do `docker` com diferentes níveis de complexidade. <br>

## Estrutura do Projeto

Cada comando deverá ser escrito em seu próprio arquivo.

Para isto, siga os seguintes passos:

1. Leia o requisito e crie um arquivo chamado commandN.dc no diretório docker-commands, onde N é o número do requisito. Por exemplo:

        Requisito 1: ./docker/docker-commands/command01.dc
        Requisito 2: ./docker/docker-commands/command02.dc
        Requisito 3: ./docker/docker-commands/command03.dc
   
2. Escreva neste arquivo o comando do CLI (Interface de Linha de Comando) do Docker que resolve o requisito. Um exemplo de como vai ficar seu arquivo:
   
         docker network inspect bridge
   
Os arquivos principais do projeto estão na pasta `docker`, na raiz do projeto. Nela estão contidos:
  1.  Pasta `docker-commands`: onde ficarão os comandos exigidos pelos requisitos;
      - ⚠️ __Importante: você deve assumir que essa é a pasta raiz para os comandos.__
      - Por exemplo, se você precisa referenciar um caminho em um comando, você deve assumir que sua pasta raiz esta partindo de ./docker.
  2. Pasta todo-app: onde fica a nossa pseudo-aplicação, que servirá como base para nossos `Dockerfiles` e `Compose`;
      - ⚠️ __Essa aplicação conta com um README.md próprio, que pode ser usado como referência na criação dos dockerfiles e do docker-compose.yml!__

Quando for necessário fazer a orquestração das aplicações, o arquivo `docker-compose.yml` deverá ser criado na pasta `./docker`. conforme o arquivo de exemplo `docker/docker-compose.yml.example`.
   
## Instalação

1. Clone o repositório com o comando: `git clone git@github.com:aimemartins/project-docker-todo-list.git`
2. Entre na pasta do repositório que você acabou de clonar: `cd project-docker-todo-list`
3. Execute o comando `npm install` para instalar as dependências.
   
## Testes

⚠ É necessário ter o Docker instalado corretamente na sua máquina para rodar os testes locais.


1. Todos os requisitos do projeto serão testados automaticamente por meio do Jest.
   - Para testar todas funções no terminal, basta executar o comando abaixo:
     ```sh
       npm test
   - Você pode rodar um arquivo de test por vez, exemplo:
      ```sh
      npm test 01container

⚠ Atenção: ⚠ Não utilize a função .only ou .skip após o describe. Os testes precisam rodar por completo para que o projeto seja avaliado localmente.


### Cobertura de testes

 - Essa cobertura avalia a eficácia dos testes implementados de acordo com os requisitos, determinando se cobrem o que foi pedido ou não. Para executar e acompanhar a implementação da sua cobertura de testes, rode o comando abaixo:
   ```sh
   npm run test:coverage
   
## Status
O projeto está finalizado com 100% dos requisitos  ✅ 

## Requisitos 
   
   ### Requisitos Obrigatórios

   #### Comandos Docker
   
   1. Crie um container em modo interativo, sem rodá-lo, nomeando-o como `01container` e utilizando a imagem `alpine` na versão `3.12` <br>
O avaliador executará o comando no arquivo `command01.dc`. <br> <br>
      __Observações técnicas__ <br>
      - O container não deve ser inicializado, somente criado;
      - O container deve estar preparado para acesso interativo.<br> <br>
      __Dicas__ <br>
      - Dê uma olhada no comando `create`; 😉
      - Lembre-se que um parâmetro não é necessariamente aplicável a apenas um comando;
      - Consulte sempre que possível a Documentação Oficial sobre comandos básicos;
      - Lembre-se que a esmagadora parte dos comandos docker recebe parâmetros (opções).

        
   2. Inicie o container `01container`. <br>
O avaliador executará o comando no arquivo command02.dc.<br> <br>
      __Observações técnicas__ <br>
      - O container `01container`, que acabou de ser criado e está parado, deve ser iniciado;
      - Se o container tiver sido iniciado de modo interativo, ele deve se manter ativo ao iniciá-lo.
        
   3. Liste os containers filtrando pelo nome `01container`. <br>
O avaliador executará o comando no arquivo command03.dc. <br> <br>
       __Dicas__ <br>
      - Praticamente todo comando de listagem no Docker possui uma forma de filtragem.
        
   4. Execute o comando `cat /etc/os-release` no container `01container` sem se acoplar a ele. <br>
O avaliador executará o comando no arquivo command04.dc.<br> <br>
       __Dicas__ <br>
      - É possível fazer isso sem usar o comando `attach`.
        
        
   5. Remova o container `01container`. <br>
O avaliador executará os comandos nos arquivos `command05.dc` e `command03.dc`.
      
        
   6. Faça o download da imagem `nginx` com a versão `1.21.3-alpine` sem criar ou rodar um container. <br>
O avaliador executará o comando no arquivo `command06.dc`.
      
   7. Rode um novo container com a imagem `nginx` com a versão `1.21.3-alpine` em segundo plano nomeando-o como `02images` e mapeando sua porta padrão de acesso para porta `3000` do sistema hospedeiro
O avaliador executará o comando no arquivo `command07.dc`.<br> <br>
    __O que será testado__<br>
      - Que o container foi iniciado corretamente;
      - Que é possível ter acesso ao container pelo endereço `localhost:3000`;
      - Que a página retorna o valor esperado.
      
      
   8. Pare o container `02images` que está em andamento. <br>
O avaliador executará o comando no arquivo `command08.dc`.

   #### Dockerfile
       
   9. Gere uma build a partir do Dockerfile do `back-end` do `todo-app` nomeando a imagem para `todobackend`
          - Implemente a função getSchedule que irá disponibilizar um cronograma com os horários de visita da semana disponíveis para cada espécie de animal. <br> <br>
      Escreva no arquivo `command09.dc` um comando que fará o `build`(documentação do comando) de uma imagem a partir do arquivo `./docker/todo-app/back-end/Dockerfile`, esta imagem deve ter o nome `todobackend`. <br>
      No arquivo `./docker/todo-app/back-end/Dockerfile` escreva os comandos que farão com que a imagem:
        - rode a partir da imagem do `node` na versão 14;
        - exponha a porta `3001`;
        - adicione o arquivo `node_modules.tar.gz` à imagem;
        - copie todos os arquivos da pasta `back-end` para a imagem. (você pode usar o caminho relativo, lembrando que a Dockerfile está em `./docker/todo-app/back-end/Dockerfile`);
        - inicie a aplicação com o comando `npm start`.
        - Nesse contexto, deve-se criar um arquivo Dockerfile na pasta `./docker/todo-app/back-end/`, que será utilizado com comando exigido no requisito;
        - Esse arquivo deve buscar reproduzir as etapas de `back-end` contidas no `README.md` da pseudo-aplicação;
        - O avaliador executará o comando no arquivo `command09.dc`. <br>
         __Dicas__ <br>
      - O comando ADD do Dockerfile, também pode ser utilizado para descompactar arquivos dentro do container. Entenda a diferença entre o comando ADD e COPY.
          
   10.  Gere uma build a partir do Dockerfile do `front-end` do `todo-app` nomeando a imagem para `todofrontend`. <br>
Escreva no arquivo `command10.dc` um comando que fará o `build`(documentação do comando) de uma imagem a partir do arquivo `./docker/todo-app/front-end/Dockerfile`, esta imagem deve ter o nome `todofrontend`.
        - No arquivo `./docker/todo-app/front-end/Dockerfile` escreva os comandos que farão com que a imagem:
            - rode a partir da imagem do `node` na versão 14;
            - exponha a porta `3000`;
            - adicione o arquivo `node_modules.tar.gz` à imagem;
            - copie todos os arquivos da pasta front-end para a imagem. (você pode usar o caminho relativo, lembrando que a Dockerfile está em `./docker/todo-app/front-end/Dockerfile`);
            - inicie a aplicação com o comando `npm start`.
         - Nesse contexto, deve-se criar um arquivo Dockerfile na pasta `./docker/todo-app/front-end/`, que será utilizado com comando exigido no requisito;
         - Esse arquivo deve buscar reproduzir as etapas de front-end contidas no README.md da pseudo-aplicação para que ele rode corretamente;
         - O avaliador executará o comando no arquivo `command10.dc`.
         __Dicas__ <br>
      - O comando ADD do Dockerfile, também pode ser utilizado para descompactar arquivos dentro do container. Entenda a diferença entre o comando ADD e COPY.
        
         
   11.  Gere uma build a partir do Dockerfile dos `testes` do `todo-app` nomeando a imagem para `todotests`. <br>
        - Escreva no arquivo `command11.dc` um comando que fará o `build`(documentação do comando) de uma imagem a partir do arquivo `./docker/todo-app/tests/Dockerfile`, esta imagem deve ter o nome `todotests`.<br>
        - No arquivo `./docker/todo-app/tests/Dockerfile` escreva os comandos que farão com que a imagem:
           - rode a partir da imagem do `mjgargani/puppeteer:trybe1.0`;
           - adicione o arquivo `node_modules.tar.gz` à imagem;
           - copie todos os arquivos da pasta tests para a imagem. (você pode usar o caminho relativo, lembrando que a Dockerfile está em `./docker/todo-app/tests/Dockerfile`);
           - inicie os testes com o comando `npm test`.
         
  

   ### Requisitos Bônus
   #### Docker-compose

   12. Suba uma orquestração em segundo plano com o docker-compose de forma que `backend`, `frontend` e `tests` consigam se comunicar
   - O avaliador executará o comando no arquivo command12.dc. Este comando pressupõe a existência do arquivo `./docker/docker-compose.yml`.
   - O docker-compose deve rodar na versão 3 ou superior.
   - Dicas
Use as imagens já "buildadas" que foram executadas nos requisitos 9, 10 e 11 para a criação do compose;
Consulte a documentação em ./docker/todo-app/README.md;
É possível adicionar e extrair arquivos .tar.gz no Dockerfile com apenas um comando.

       


