
sudo su - web  // ctmd ***user for heal***


cd dashboard  // /var/opt/ctmd ***for heal***

### Make backup

docker exec -it ctmd-pipeline /bin/bash

curl -X POST localhost:5000/backup

ls /backup

***rename backup to something more easy to use, like backup1***

mv '2022-12-13 18:08:45.795183' backup1
exit 

### Bring docker containers down

docker-compose  -f docker-compose.prod.yml down

cd ..

cp -r dashboard/ dashboardbackup

cd dashboard

### Get release by tag name
git checkout v2.13

cd ..

### Recreate data folder
rm -r ./dashboard/db/data

mkdir ./dashboard/db/data

### Bring docker containers up

cd dashboard

USER=$(id -u):$(id -g) docker-compose  -f docker-compose.prod.yml up --build -d -V


### Check db logs
docker logs ctmd-db

### Restore DB backup (in our case backup name is backup1)
docker exec -it ctmd-pipeline /bin/bash

curl -X POST localhost:5000/restore/backup1

exit

### Run SQL scripts

docker exec -it ctmd-db psql -U postgres -d duketic

OR

docker exec -it ctmd-db psql -U healctmduser -d healctmddb
