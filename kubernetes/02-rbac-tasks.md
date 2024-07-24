## Description

News-aggregator deployment should use service account with a limited list of permissions which are needed only for the app.
To achieve that, you will need to do next:
1. Create `ServiceAccount` resource.
2. Create `Role` resource.
3. Create `RoleBinding` resource.
4. Update news-aggregator `Deployment` to use the service account.