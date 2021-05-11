##CTMD Release Process

###ssh into stage-ctmd/dev-ctmd/ctmd.edc.renci.org
```
ssh stage-ctmd.edc.renci.org
```
###log-in as 'web' user
```
sudo su - web
```
###Clone HEAL-data-mapping repository, if it's not there already
```
git clone https://github.com/RENCI/HEAL-data-mapping.git
```
###Update HEAL-data-mapping
```
cd HEAL-data-mapping
git branch
git pull origin master
```
###Checkout appropriate branch
```
cd ..
cd dashboard/
git branch
git fetch origin
git checkout <release-branch>
git branch    #check if you are on the right branch
```
###At this point, try to recollect the changes that were made for this release. If there are only frontend changes, check out your branch and run:
```
docker-compose -f docker-compose.prod.yml up --build -d -V –no-deps frontend
```
###Check if the release version is correct
```
cat docker-compose.prod.yml
```
###Check if 'data' folder exists
```
cd db/
ls
```
###Remove 'data' folder
```
cd ..
docker-compose -f docker-compose.prod.yml down
exit
sudo su
cd ..
cd web/dashboard/db/
ls
rm -rf data
cd ..
exit
sudo su - web
cd dashboard/
```
###Check if 'data' folder is gone
```
cd db/
ls
```
###Deployment
```
cd ..
ls
docker-compose -f docker-compose.prod.yml up --build -d -V
```