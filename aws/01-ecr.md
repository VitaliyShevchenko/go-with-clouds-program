### AWS ECR

Amazon Elastic Container Registry (Amazon ECR) is an AWS managed container image registry service that is secure,
scalable, and reliable.

In the scope of this task, you need to store all docker images and helm charts in **private ECR**.

This task will require below updates:

1. Create ECR repos in your region using creds which were given to you.
2. Update `Taskfile` to be able to push images/charts to ECR.
3. Update GithubActions to trigger `Taskfile` tasks.
4. Create a k8s `CronJob` which will create a k8s `Secret` with credentials to ECR.
5. Update all k8s deployments to use the secret to pull images from ECR.

### Useful links

* [ECR](https://aws.amazon.com/ecr/)
* [Pull images from private ECR](https://skryvets.com/blog/2021/03/15/kubernetes-pull-image-from-private-ecr-registry/)
* [Using Secrets in GitHub Actions](https://docs.github.com/en/actions/security-for-github-actions/security-guides/using-secrets-in-github-actions)