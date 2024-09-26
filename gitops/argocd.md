### GitOps

- Every chart you deploy on your cluster needs to be provisioned via gitops (except for the argo-cd chart, which is allowed to be installed out-of-band).
  - First, get familiar with argo docs: https://argo-cd.readthedocs.io/en/stable/
  - Also, nice to go through this overview, which hightlights some important details: https://codefresh.io/learn/argo-cd/
- You can experiment with different approaches how to structure your gitops mechanism.
  - App manifests and infrastructure manifests can be placed either in the same git repository with your code, or in a different repository but with clear separation between application code and operations configurations. The first approach is usually preferable for larger projects.
  - You can combine kustomize, helm charts and argo apps in any structure.
    - Using argo for kustomize: https://argo-cd.readthedocs.io/en/stable/user-guide/kustomize/
    - Using argo for helm: https://argo-cd.readthedocs.io/en/stable/user-guide/helm/
    - AppOfApps pattern: https://argo-cd.readthedocs.io/en/stable/operator-manual/cluster-bootstrapping/
- Ideally, gitops engine, argo-cd chart (and dependencies if any) in our case, should be part of the CDK stack, so nothing should be getting installed manually. 

