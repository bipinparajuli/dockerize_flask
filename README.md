# Docker
 Project intented to learn docker, where i try to dockerize simple flask application.


### create a app container from docker image
```
docker build -t flask_app:1.0 . 
```

### pull and run mysqldb container 
```
docker run --name mysql -d -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=backend -e MYSQL_USER=testuser -e MYSQL_PASSWORD=admin123 -v <Path/to/Project/>/Docker/db/init.sql:/docker-entrypoint-initdb.d/init.sql mysql/mysql-server:5.7 
```

### run the app container by linking the host to communicate with db container
```
docker run --link "mysql:backenddb" -p 5000:5000 flask_app:1.0.
```
