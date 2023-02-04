## Firebase Deploy Workflow

Builds Nuxt app and deploy to Firebase Hosting and Firebase Cloud Functions

## Usage

```yaml
jobs:
  deploy:
    name: Deploy
    uses: chika3742/firebase-deploy/workflow.yml@main
    with:
      # nuxt-build-path: 
      # functions-path: 
      workload-identity-provider: 
      service-account: 
      workload-identity-audience: 
    secrets:
      fcm-vapid-key: 
```

### Inputs

| key                        | required | description                           |
|----------------------------|----------|---------------------------------------|
| nuxt-build-path            | No       | Path to the nuxt source to build      |
| functions-path             | No       | Path to the functions to deploy       |
| workload-identity-provider | Yes      | ID of the workload identity provider  |
| service-account            | Yes      | Service account to use when deploying |
| workload-identity-audience | Yes      | Audience of the workload identity     |

### Secrets

| key           | required | description                                      |
|---------------|----------|--------------------------------------------------|
| fcm-vapid-key | No       | (if used) VAPID Key for Firebase Cloud Messaging |