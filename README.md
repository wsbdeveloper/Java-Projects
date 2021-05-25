
<p align="center">
  <a href="https://unform.dev">
    <img src="http://catalisi.com.br/wp-content/uploads/2020/10/catalisi-cerveja-ze-delivery-expansao-ambev-brasil.jpg" alt="Unform" />
  </a>
</p>

<p align="center">Desafio Backend Zé Delivery! 🚀</p>



# Desafio Backend
![Badge](https://img.shields.io/static/v1?label=License&message=MIT&color=green&style=plastic)
![Badge](https://img.shields.io/static/v1?label=Node&message=14&color=yellow&style=plastic)
![Badge](https://img.shields.io/static/v1?label=Mongodb&message=LTS&color=greenw&style=plastic)

## Overview
Precisamos fornecer uma aplicação backend com arquitetura API REST, nossa API deve fornecer pdvs (Pontos de Vendas) com uma certa região de atendimento pelo Zé Delivery


### Pré-requisitos

Antes de inciar, você terá que ter instalado em sua máquina ou servidor as seguintes ferramentas:
[Git](https://git-scm.com), [Node.js](https://nodejs.org/en/)

### :computer: Executando a aplicação backend configuração inicial (servidor)

```bash
# Clone este repositório
$ git clone <https://github.com/tgmarinho/nlw1>

# Acesse a pasta do projeto no terminal/cmd
$ cd ze_backend

# Instale as dependências
$ npm install

# Antes de executar devemos configurar as variáveis de ambiente
# no diretorio raiz backend
# criaremos os arquivos de controle configure conforme seu ambiente
# desenvolvimento, teste ou produção.
touch .env.production
# Windows Powershell
New-Item -Path '.env.production'

# Execute a aplicação
$ npm run-script run
```

### MongoDB configuração arquivo .env

* mongoCluster="cluster0.sambu.mongodb.net"
* mongoUser="Provi"
* mongoPass="*multiway+23"
* mongoDatabase="pdvs"
* PORT=<int: número>

### Especificação técnica

<p> Declaramos a camada de modelo com estratégia de acordo com o nosso banco de dados, estruturei para uma forma separada:

```bash
├── src
│   ├── controller
│   │   ├── store
│   │   │   ├── store.js
│   │   │   ├── storeMiddleware.js
│   ├── model
│   │   ├── strategys
│   │   │   ├── mongodb
│   │   │   │   ├── documents
│   │   │   │   │   ├── documents
│   │   │   │   │   │   ├── docPdvs.js
│   │   │   │   │   ├── mongodb.js
│   ├── routers
│   │   ├── routersManagement.js
│   ├── utils
│   │   ├── mocks
│   │   │   ├── coordinatesMock.js
│   │   │   ├── curl.sh
│   ├── index.js
│   ├── test
│   │   ├── pdvs.test.js
├── dist
├── node_modules
├── .env.development
├── .env.production
├── .env.test
├── README.md
├── package.json
├── .eslintrc.json
├── .prettierrc.json
├── .travis.yml
└── .gitignore
```

### Models
<p> Os modelos são representação da camada de banco de dados, estou abordando de forma separada por estratégias de banco de dados.
Atribuir uma estrutura que nos permite a separação de diferentes abordagens de databases statregys/mongodb e podemos utilizarmos outro abordagem
como strategys/postgresql e realizar as configurações.
</p>

### Controllers
<p> Os controles da aplicação servem para receber e processar nossos dados a partir das chamadas via http. Podemos verificar na estrutura que 
  criei uma sub-pasta <i>controller/store</i> dentro utilizo o controle de arquivos como um pelo gerenciamento e controle <i>store.js</i> e outro
  pelo gerenciamento dos caminhos para API REST (Middlewares).
</p>

### Routers
<p>
  Responsável pelo gerenciamento de configuração dos <i>Middlewares</i> o arquivo <i>routersManagement</i> será responsável pelo agrupamento de rotas
  definimos as chamadas dentro dos <i>Controllers Middlewares</i> de cada controlador pelo arquivo.
</p>


### Arquivos de configuração

<p> Configuração de regras de código e sintaxe com prettier e eslint com os arquivos <i>.eslintrc.json</i> e <i>.prettierrc.json</i> com ele definimos padrões e regras para escrita de código, deixando de uma obrigação (automática) de escrita no código.</p>

<p> Controle de váriaveis de ambiente com os arquivos :</p>

- <i>.env.development</i>
- <i>.env.test</i>
- <i>.env.production</i>  

<p> <i>.travis.yml</i> responsável pela configuração de deploy, configurações e validações utilizando o travis ci</p>

- [Travis CI](https://travis-ci.org)

<p> Diretório <b>utils</b>, tem como função nos auxiliar com arquivos e/ou arquivos javascript para utilizações durante o desenvolvimento do sistema.
  Atribui um arquivo de <i>Mock</i> para representar coordenadas reais do nosso boss Zé rs, brincadeiras a parte, teremos um diretório com papel de nos auxiliar para alguns pontos separados dos nossos diretórios com obrigatóriedade de sintaxes e padrões, até para questões de organização dos arquivos. 
</p>

<p> <b>DIST</b>, diretório será atribuídos os arquivos de distribuição para os sistemas operacionais Windows e Linux com arquitetura de processamento x64 bits </p>  

### 🛠 Tecnologias

As seguintes ferramentas foram usadas na construção do projeto:

- [Node.js](https://nodejs.org/en/)
- [NPM](https://www.npmjs.com/get-npm)
- [GIT](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

### :gem: Membros / :punch: :pray: Agradecimentos

<p align="rigth">
  <a href="https://www.linkedin.com/in/wellington-bezerra-dev/">
    <img src="https://avatars.githubusercontent.com/u/37592985?s=100" width="100" height="100" alt="Unform" />
  </a>
</p>

#### Wellington da Silva Bezerra

<p>
  Queria agradecer o Victor Romero, que foi um cara que me proporcionou a possibilidade de entrar no Zé,
  espero ter atendido os requisitos e fazer parte de empresa maravilhosa! :star:
</p>

- [LinkedIn](https://www.linkedin.com/in/wellington-bezerra-dev/)
- [GitHub](https://github.com/wsbdeveloper)
- [HackerHank](https://www.hackerrank.com/wellingtons_bez1)
