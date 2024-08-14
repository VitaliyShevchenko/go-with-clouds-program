The application should be packaged to Helm (one of the available package managers) chart. This will allow defining,
installing,
and upgrade even the most complex Kubernetes application.
All k8s manifests for HTTPs news-aggregator should be located under appropriate chart and under `templates` resources.

In addition to that the following Taskfile tasks should be added:

1. `createChart` — creates a Helm chart with all needed resources for the news-aggregator
2. `installChart` — installs chart on Kubernetes cluster
3. `uninstallChart` — uninstalls chart from Kubernetes cluster

A list of fields which a user/admin can dynamically populate:

```yaml
replicaCount: <replicaCount>
containerPort: <containerPort>
imageName: <imageName>
namespace: <namespace>
# if not defined, then default service account should be used
serviceAccount: <string>
resources:
  limits:
    cpu: <cpu_limit>
    memory: <memory_limit>
  requests:
    cpu: <cpu_request>
    memory: <memory_request>
# will be added later, but helm values can be created now
autoscaling:
  enabled: <enabled>
  minReplicas: <minReplicas>
  maxReplicas: <maxReplicas>
  targetCPUUtilizationPercentage: <targetCPUUtilizationPercentage>
```
