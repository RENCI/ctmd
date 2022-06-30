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
CTMD_DOCKER_FLAGS="-f docker-compose.prod.yml"
```
### conditional code:

for stage-ctmd.edc.renci.org, use 
```
CTMDHOST=stage-${CTMDHOST}
```
for dev-ctmd.edc.renci.org, use 
```
CTMDHOST=dev-${CTMDHOST}
CTMD_DOCKER_FLAGS="-f docker-compose.yml"
```
for demo-ctmd.edc.renci.org, use 
```
CTMDHOST=demo-${CTMDHOST}
CTMD_DOCKER_FLAGS="-f docker-compose.yml"
```
for heal-ctmd.edc.renci.org, use:
```
CTMDUSER=cmtd
CTMDROOT=/var/opt/ctmd
CTMDHOST=heal-${CTMDHOST}
```
### For all servers:
```
# see above for the value of CTMDHOST variable
ssh ${CTMDHOST}.edc.renci.org
sudo su -${CTMDUSER}
# set the variables, see above
cd ${CTMDROOT}/dashboard
docker-compose ${CTMD_DOCKER_FLAGS} down
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
# set RELEASE_BRANCH to your release, e.g., 
# RELEASE_BRANCH=2.10
```
If deploying to stage, don't forget to **create RELEASE_BRANCH** off master; it may be easiest to do this from github.
```
cd ..
cd dashboard/ (NOTE: Please remember cloning https://github.com/RENCI/ctmd-dashboard.git and rename it using- mv ctmd-dashboard dashboard, if it's not there already)
git fetch origin
git branch -v -a |grep ${RELEASE_BRANCH}
# remotes/origin/${RELEASE_BRANCH}
git checkout -b ${RELEASE_BRANCH}
# may need to do this too:
git branch --set-upstream-to=origin/${RELEASE_BRANCH} ${RELEASE_BRANCH}
git branch    #check if you are on the right branch
git pull
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

### At this point, try to recollect the changes that were made for this release

### Check if the release version is correct
```
cat docker-compose.prod.yml
```
### Deployment
```
USER=$(id -u):$(id -g) docker-compose ${CTMD_DOCKER_FLAGS} up --build -d -V
```
Once ${CTMDROOT}/db/data has been created, you need to change the permissions on it so the ctmd-db will work; log into a different shell so you can use sudo permissions, set the variables (see above) and execute:
```
sudo chown ${CTMDUSER} ${CTMDROOT}/dashboard/db/data
```
Check to be sure the permission change worked with:
```
docker logs ctmd-db
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
