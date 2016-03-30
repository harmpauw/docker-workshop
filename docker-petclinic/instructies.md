mvn package -DskipTests package

# mappen aanmaken
docker/
docker/app
docker/database_data

# docker netwerk aamaken
docker network create petclinic

# container voor MySQL opstarten
docker run --net=petclinic -d --name mysql -v /home/workshop/docker/database_data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=secret -e MYSQL_DATABASE=petclinic -e MYSQL_USER=petclinic -e MYSQL_PASSWORD=petclinic mysql

# image maken op basis van tomcat en daarna starten
petclinic.war kopieeren naar app/ 
docker build -t petclinic app/
docker run --net=petclinic --rm -it --link mysql:mysql -p 8080:8080 petclinic

# alles afsluiten
ctrl + c
docker ps
docker stop mysql
docker rm mysql
docker network rm petclinic

# docker-compose