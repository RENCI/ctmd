## CTMD Backup Process

Please follow the steps below to manually backup data, when needed:
<pre>
<b>Backup commands</b>
docker exec -it ctmd-pipeline /bin/bash
curl -X POST localhost:5000/backup

<b>Look for backup</b>
docker exec -it ctmd-pipeline /bin/bash
ls /backup

<b>Data restoration commands</b>
docker exec -it ctmd-pipeline /bin/bash
curl -X POST localhost:5000/restore/<i>backup name replace space by %20</i>

<b>Check if the task is done</b>
curl -X GET localhost:5000/task
</pre>
