### AWS Secrets Manager

AWS Secrets Manager helps you manage, retrieve, and rotate database credentials, application credentials, OAuth tokens,
API keys, and other secrets throughout their lifecycles. Many AWS services store and use secrets in Secrets Manager.

It's a good solution to store all keys, passwords, credentials, which we are using in the news-aggregator application.
In the scope of this task, below items must be integrated:
1. Install [aws-secrets-manager](https://external-secrets.io/latest/provider/aws-secrets-manager/) 3rd party helm chart.
2. Create secrets in `AWS Secrets Manager` with all sensitive data which is used in news-aggregator.
3. Create `ExternalSecretStore` and `ExternalSecret` k8s object to pull secrets from `AWS Secrets Manager` to EKS cluster.