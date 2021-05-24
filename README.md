
<p align="center">
  <a href="https://unform.dev">
    <img src="http://catalisi.com.br/wp-content/uploads/2020/10/catalisi-cerveja-ze-delivery-expansao-ambev-brasil.jpg" alt="Unform" />
  </a>
</p>

<p align="center">Desafio Backend Zé Delivery! 🚀</p>



# Desafio Backend
![Badge](https://img.shields.io/static/v1?label=License&message=MIT&color=green&style=plastic)
![Badge](https://img.shields.io/static/v1?label=Node&message=14&color=yellow&style=plastic)
![Badge](https://img.shields.io/static/v1?label=Mongodb&message=14&color=greenw&style=plastic)

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
│   ├── css
│   │   ├── **/*.css
│   ├── favicon.ico
│   ├── images
│   ├── index.html
│   ├── js
│   │   ├── **/*.js
│   └── partials/template
├── dist (or build)
├── node_modules
├── bower_components (if using bower)
├── test
├── Gruntfile.js/gulpfile.js
├── README.md
├── package.json
├── bower.json (if using bower)
└── .gitignore
```

### 🛠 Tecnologias

As seguintes ferramentas foram usadas na construção do projeto:

- [Node.js](https://nodejs.org/en/)
- [NPM](https://www.npmjs.com/get-npm)
- [GIT](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
