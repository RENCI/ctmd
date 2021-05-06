# ctmd

## Dependencies

* Back-end:

Deploys a image to dockerhub

Detailed documentation here: https://github.com/RENCI/tic-map-pipeline-script

* Front-end:

Accesses the backend image directly from dockerhub, via docker-compose

Detailed documentation here: https://github.com/RENCI/ctmd-dashboard

## Application Containers

container       | repository
--------------- | --------------
`ctmd-pipeline` | [txscience/ctmd-pipeline-reload](https://github.com/txscience/ctmd-pipeline-reload)
`ctmd-api`      | [RENCI/ctmd-dashboard](https://github.com/RENCI/ctmd-dashboard)
`ctmd-db`       | [RENCI/ctmd-dashboard](https://github.com/RENCI/ctmd-dashboard)
`ctmd-frontend` | [RENCI/ctmd-dashboard](https://github.com/RENCI/ctmd-dashboard)
`ctmd-redis`    | [RENCI/ctmd-dashboard](https://github.com/RENCI/ctmd-dashboard)
