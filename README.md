# RSS-Mobile-Reader
 
## Descrição:
Esta aplicativo serve para rapidamente coletar artigos de noticias dos site Raspberry PI News, OmgUbuntu (Linux Ubuntu) e Blender Nation. Ele mostrar de forma rapida um resumo do conteudo e links para os artigos

Este sistema usa o serviço de RSS para coletar a informação e tambem disponelizar um link de acesso para o propio artigo.

Ele também deixa o usuario favoritar artigos, essa informação é guardada em uma database MySQL.

## Dependencias:
 - react-navigation/native
 - react-navigation/native-stack
 - axios
 - expo
 - expo-status-bar
 - react
 - react-native
 - react-native-rss-parser
 - react-native-safe-area-context
 - react-native-screens
 - react-native-rss-parser
 - cors
 - dotenv
 - express
 - mysql2
 - nodemon

## Antes de instalar Instalar:
### Instale Node.js
[Node.JS](https://nodejs.org/en)

### Instale yarn
```
npm install --global yarn
```
## Como Instalar:
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

### Veja o video
 - [LINK](https://www.youtube.com/watch?v=s1XEDgDe-0A)

## Screenshots
![Image 1](https://i.ibb.co/Hq4cQjq/Screenshot-20230609-143311-Expo-Go.jpg)
![Image 2](https://i.ibb.co/hLLWHXJ/Screenshot-20230609-143331-Expo-Go.jpg)
![Image 3](https://i.ibb.co/c65sc4W/Screenshot-20230609-143342-Expo-Go.jpg)
![Image 4](https://i.ibb.co/Yjy1L1Z/Screenshot-20230609-143352-Expo-Go.jpg)
![Image 5](https://i.ibb.co/HxKpyYx/Screenshot-20230609-143401-Expo-Go.jpg)
