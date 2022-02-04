# go-geolocation
<p align="center">CRUD for users and address registration via geolocation.</p>
<img src="http://img.shields.io/static/v1?label=STATUS&message=UNDER%20DEVELOPMENT&color=RED&style=for-the-badge"/>


### Features
- [ ] Implement the global system position(GPS).
- [ ] When entering the address this application will show the geolocation of the entered address storing asynchronously in the database.

## Requirements
* go 1.17.3
* PostgreSQL 12.9
## Steps for using this application
1. Clone this repo or ``go get github.com/wesleymsan/go-geolocation``
2. You need to have [PostgreSQL](https://www.digitalocean.com/community/tutorials/how-to-install-postgresql-on-ubuntu-20-04-quickstart-pt) installed on your machine.
3. Create the database: ``geolocation_api``
4. Create the user in the database: ``CREATE USER username WITH PASSWORD 'password';``
5. Run in your terminal: ``go run main.go
``

### Testing in Postman(``http://localhost:8080``): 

| Endpoint | Method| Note|
|----------|:-----:|:-----:|
| /users   | GET   |Will provide login and password
| /users/{id} | GET|Will provide login and password
| /posts | GET|Will provide all database
| /login | POST|Use login and email, will provide token
| /users/{id} | DELETE|Athorization: Bearer Token
| /users/{id} | PUT|Athorization: Bearer Token
| /users | GET|No token required
| /posts/{id} | PUT| Athorization: Bearer Token
| /posts | POST|Athorization: Bearer Token
| / | GET|No token required

## Run the tests
1. Create the database for tests: 
<br>``sudo -u postgres createdb geolocation_api_test``
2. Run the test in ``/tests/modeltests`` and ``/tests/controllertests`` dir:
<br>``go test -v``
3. You can run all tests in ``/tests``
<br>``go test -v ./...``
