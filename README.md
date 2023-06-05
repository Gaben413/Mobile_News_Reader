# RSS-Mobile-Reader
 
## Descrição:
Esta aplicativo serve para rapidamente coletar artigos de noticias do site Raspberry PI News e mostrar de forma rapida um resumo do conteudo.
Este sistema usa o serviço de RSS para coletar a informação e tambem disponelizar um link de acesso para o propio artigo

## Dependencias:
 - [Node.JS](https://nodejs.org/en)

 - [Yarn](https://www.npmjs.com/package/yarn)

```
npm install --global yarn
```

 - [react-native-rss-parser](https://www.npmjs.com/package/react-native-rss-parser)

```
npm install react-native-rss-parser --save
```

## Instalar:
Clone o repositorio
```
git clone https://github.com/NowhereCat/RSS-Mobile-Reader.git
```

### Client
Va para a pasta client
```
cd client
```

Instale as depencencias
```
yarn install
```

Crie um arquivo .env com a sequinte estrutura:
```Dotenv
SUBMIT_IP=http://[IP DO SERVIDOR]:3001/item
FETCH_IP=http://[IP DO SERVIDOR]:3001/itens
DELETE_IP=http://[IP DO SERVIDOR]:3001/item
```
Substitua o [IP DO SERVIDOR] com o IP do servidor
EX:
http://192.0.0.0:3001/item

### Database
Crie uma database em MySQL, com a estrutura sequinte:
```SQL
CREATE TABLE Favourite(
    favID INT PRIMARY KEY AUTO_INCREMENT,
    title VARCHAR(255) NOT NULL,
    descr VARCHAR(255) NOT NULL,
    link VARCHAR(255) NOT NULL,
    published VARCHAR(255),
    sourceType CHAR(1) DEFAULT('R'),
    CHECK(sourceType = 'R' OR sourceType = 'U' OR sourceType = 'B')
);
```

### Server
Va para a pasta server
```
cd server
```

Instale as depencencias
```
yarn install
```

Crie um arquivo .env com a sequinte estrutura:
```Dotenv
HOST="localhost"
USER="root"
PASSWORD="password"
DB="rss_reader"
PORT=3306
```
Substitua o Host, Usuario, Schema, senha e port escrito no arquivo .env, para ser os mesmos da database que foi criada.

## Iniciar Projeto
Primeiro inicio o servidor:
```
cd server
npm run dev
```

Depois inicie o projeto cliente e abrao em aplicativo EXPO
```
cd client
yarn start
```

## Como usar:

### Clique no botão superior a direita para carregar ou recarregar a informação RSS
![](https://i.ibb.co/jJJFm8N/1.png)![](https://i.ibb.co/J20qyPz/2.png)

### Logo os 10 ultimos artigos de noticias serão carregados abaixo, com o titulo, descrição, link e data de postagem
![](https://i.ibb.co/R0WKBhy/3.png)

### Você pode digitar algo na barra de pesquisa para achar algo especifico
![](https://i.ibb.co/Mk3kVtz/4.png)
