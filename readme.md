# Vue 3 + Strapi 3 + MySQL dockerized 
This project contains a dockerized vue app with a strapi 3 and mysql backend. 

## Follow these steps to set up the project

1. Clone from github
    ```
    git clone https://github.com/msjo36725/strapi-mysql
    ```
2. Go to the project root folder
    ```
    cd strapi-mysql
    ```
3. Run docker compose. This might take some minutes.
    ```
    docker compose up
    ```
4. If you want to remain control over your terminal, run it detached instead.
    ```
    docker compose up -d
    ```
5. Once the compose is done you can access the app on the following links
    - [Vue App](http://localhost:8080/)
    - [Strapi Api](http://localhost:1337/admin)

Use the following credentials to login to the Strapi admin

    ms@awakethewater.com
    SM#b2%s8Q_tLnki
    



## Want to run the Vue app in production stage?

Make the following changes to docker-compose.yml

```
  vue:
    build:
      context: ./recipe-app
      target: 'production-stage'
    ports:
      - '8080:80'
```