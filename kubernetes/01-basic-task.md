#### Pre requirements
Install **kubectl**, **Lens**, **Docker Desktop** (if not installed)

A kubernetes cluster in docker should be created. The news-aggregator web server should have an ability 
to be deployed/undeployed on/from this cluster.

To achieve that, you will have to do next:
1. Create `templates` folder in the project. (most of the time all k8s related files are located here)
2. Create a YAML file with a `Deployment` manifest, which will deploy news-aggregator on the cluster.
3. Create a `Service` manifest, which will allow access news-aggregator in the cluster.
4. Add `deploy` task to Taskfile — deploys news-aggregator app on the Kubernetes cluster. (Hint: `kubectl apply -f path_to_folder_with_manifests`)
5. Add `undeploy` task to Taskfile  — removes news-aggregator app from the Kubernetes cluster. (Hint: `kubectl delete -f path_to_folder_with_manifests`)
