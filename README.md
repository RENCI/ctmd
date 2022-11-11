# ctmd

## Dependencies

* Back-end:

Deploys a image to dockerhub

Detailed documentation here: https://github.com/RENCI/tic-map-pipeline-script

* Front-end:

Accesses the backend image directly from dockerhub, via docker-compose

Detailed documentation here: https://github.com/RENCI/ctmd-dashboard

* Authentication server:

Authenticates using external server, if required, as configured in ctmd-dashbaord environmental variables.

Detailed documentation here: https://github.com/RENCI/tx-autht 
Read ctmd-dashboard documentation here: https://github.com/RENCI/ctmd-dashboard#set-up-environment-variables

## Application Containers

container       | repository
--------------- | --------------
`ctmd-pipeline` | [RENCI/tic-map-pipeline-script](https://github.com/renci/tic-map-pipeline-script)
`ctmd-api`      | [RENCI/ctmd-dashboard](https://github.com/RENCI/ctmd-dashboard)
`ctmd-db`       | [RENCI/ctmd-dashboard](https://github.com/RENCI/ctmd-dashboard)
`ctmd-frontend` | [RENCI/ctmd-dashboard](https://github.com/RENCI/ctmd-dashboard)
`ctmd-redis`    | [RENCI/ctmd-dashboard](https://github.com/RENCI/ctmd-dashboard)
