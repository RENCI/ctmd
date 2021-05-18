## CTMD Release Process

### Back up the data before beginning the deployment process
Click the 'Backup' button on the ctmd/stage-ctmd/dev-ctmd/heal-ctmd website under 'Settings' in the 'Danger Zone'. To use the 'Backup' button on heal-ctmd, access level 1 is needed.

<b>Back up data using command line</b>
```
docker exec -it ctmd-pipeline /bin/bash
curl -X POST localhost:5000/backup
```

### ssh into stage-ctmd/dev-ctmd/heal-ctmd/ctmd.edc.renci.org
```
ssh stage-ctmd.edc.renci.org
```
### log-in as 'web' user
```
sudo su - web
```
### log-in as 'ctmd' user if its heal-ctmd.edc.renci.org
```
sudo su - ctmd
cd /var/opt/ctmd
```
### Clone HEAL-data-mapping repository, if it's not there already
```
git clone https://github.com/RENCI/HEAL-data-mapping.git
```
### Update HEAL-data-mapping
```
cd HEAL-data-mapping
git branch
git pull origin master
```
### Checkout appropriate branch
```
cd ..
cd dashboard/
git branch
git fetch origin
git checkout <release-branch>
git branch    #check if you are on the right branch
```
### At this point, try to recollect the changes that were made for this release. If there are only frontend changes, check out your branch and run:
```
docker-compose -f docker-compose.prod.yml up --build -d -V --no-deps frontend
```
### Check if the release version is correct
```
cat docker-compose.prod.yml
```
### Were there any changes to the HEAL-data-mapping file? If the answer is no skip the following block of code
<pre>
<b>Check if 'data' folder exists</b>
cd db/
ls

<b>Remove 'data' folder</b>
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

<b>Check if 'data' folder is gone</b>
cd db/
ls
</pre>
### Deployment
```
cd ..
ls
docker-compose -f docker-compose.prod.yml up --build -d -V
```
