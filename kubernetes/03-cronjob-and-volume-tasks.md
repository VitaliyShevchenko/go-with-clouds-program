## Description

News-aggregator server should use persistent volume instead of pod file system. This way if a pod is getting
restarted or removed, the data will not be affected.
The next requirements should be implement:
1. Persistent volume to store files with news, sources, etc. on a node host.
2. Persistent volume claim to request persistent volume.

A new `CronJob` resource should be added to the k8s manifests.
1. It should fetch latest news for all stored sources.
2. It should run once a day.
3. It should leave at least 3 successful jobs in the history and at least 1 failed job.
4. It should store latest news to the persistent volume which is being used by news-aggregator server.