## CTMD Release Process

### Get OK from Project Manager for an update outage

### Back up the data before beginning the deployment process
Click the 'Backup' button on the ctmd/stage-ctmd/dev-ctmd/heal-ctmd website under 'Settings'>'Danger Zone'. To use the 'Backup' button on heal-ctmd, access level 1 is needed.

<b>Back up data using command line</b>
```
docker exec -it ctmd-pipeline /bin/bash
curl -X POST localhost:5000/backup
```

### ssh into stage-ctmd/dev-ctmd/demo-ctmd/heal-ctmd/ctmd.edc.renci.org
```
CTMDUSER=web
CTMDROOT=/home/web
CTMDHOST=ctmd
```
### conditional code:

for stage-ctmd.edc.renci.org, use 
```
CTMDHOST=stage-${CTMDHOST}
```
for dev-ctmd.edc.renci.org, use 
```
CTMDHOST=dev-${CTMDHOST}
```
for demo-ctmd.edc.renci.org, use 
```
CTMDHOST=demo-${CTMDHOST}
```
for heal-ctmd.edc.renci.org, use:
```
CTMDUSER=cmtd
CTMDROOT=/var/opt/ctmd
CTMDHOST=heal-${CTMDHOST}
```
### For all servers:
```
ssh ${CTMDHOST}.edc.renci.org
sudo su -${CTMDUSER}
```
Please remember backing up the data, you can find the instructions here: [Backup Process](https://github.com/RENCI/ctmd/blob/main/doc/BackupProcess.md)
```
docker-compose down
mv db/data trash # this is the ctmd database, move it out of the way or docker-compose gets permission error
```
### Clone HEAL-data-mapping repository, if it's not there already
```
git clone --recursive https://github.com/RENCI/HEAL-data-mapping.git
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
cd dashboard/ (NOTE: Please remember cloning https://github.com/RENCI/ctmd-dashboard.git and rename it using- mv ctmd-dashboard dashboard, if it's not there already)
git branch
git fetch origin
git checkout <release-branch>
git branch    #check if you are on the right branch
```
### Make sure you have all the configuration files needed for deployment (.env, heal-proposals.csv, heal-users.txt, htpassword)
```
cp <.env file path> .
mkdir filter
cp <heal-proposals.csv file path> filter
cp <.htpasswd file path> frontend
cp <heal-users.txt file path> api
```

### Deploy latest pipeline, if it exists
For details, refer https://github.com/RENCI/tic-map-pipeline-script#readme

### At this point, try to recollect the changes that were made for this release. If there are only frontend changes, check out your branch and run:
```
USER=$(id -u):$(id -g) docker-compose -f docker-compose.prod.yml up --build -d -V --no-deps frontend
```
### Check if the release version is correct
```
cat docker-compose.prod.yml
```
### Deployment
```
USER=$(id -u):$(id -g) docker-compose -f docker-compose.prod.yml up --build -d -V
```
### Restore backed up data
Refer to this document- [Backup Process](https://github.com/RENCI/ctmd/blob/main/doc/BackupProcess.md)

### Ensure pipeline image version is correct
```
docker ps
```
### Update submodules in this repository to point to newest releases
```
# checkout this release recursively to get all the submodules
git clone --recurse-submodules git@github.com:/RENCI/ctmd.git
cd ctmd
git submodule update --remote
git add .
git commit -m "git submodule updated"
git push origin
```
