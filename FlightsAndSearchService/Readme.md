# Welcome to flight service

## project setup
- clone the project on your local 
- execute `npm install` on the same path of your root directory of the downloaded project
- create a `.env` file in thr root directory and add the following enviroment variable
    - `PORT = 3000`
- Inside the `src/config` folder create a new file `config.json` and then add the following peice of json

```
{
  "development": {
    "username": <YOUR_DB_LOGIN_NAME>,
    "password": <YOUR_DB_PASSWORD>,
    "database": "Flights_search_DB_DEV",
    "host": "127.0.0.1",
    "dialect": "mysql"
  }
}

```

- Once you have added your DB config as listed above, go to the src folder from your terminal and execute `npx sequelize db:create` and then execute `npm sequelize db:migrate`

## DB Design
- Airplane Table
- Flight
- Airport 

- A flight belongs to an airplane but one airplane can be used in multiple flights
- A city has many airports but one airports belongs to a city
- One airport can have many flights, but a flights belong to one airport



## Tables

### City -> id, name, created_at, updated_at
### Airport -> id, name, address, city_id, created_at, updated_at
### Relationship -> City has many airports and airport belongs to a city (one to many)
```

npx sequelize model:generate --name Airport --attributes
name:String,address:String,cityId:integer
```
