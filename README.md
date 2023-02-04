# Firebase Deploy Workflow

Nuxt 3アプリをSSGビルドし、Firebase Hosting / Firebase Cloud Functionsにデプロイするワークフローです。

## 使用方法

```yaml
jobs:
  deploy:
    name: Deploy
    uses: chika3742/firebase-deploy/.github/workflows/deploy.yml@main
    with:
      workload-identity-provider: 
      service-account: 
      workload-identity-audience: 
    secrets:
      fcm-vapid-key: 
```

※`firebase.json`は、レポジトリのルートに存在する必要があります。

### Inputs

| key                        | required                       | description                           |
|----------------------------|--------------------------------|---------------------------------------|
| nuxt-output-path           | No (default: ".output/public") | Output path of nuxt generate.         |
| functions-path             | No (default: "functions")      | Path to the functions to deploy       |
| workload-identity-provider | Yes                            | ID of the workload identity provider  |
| service-account            | Yes                            | Service account to use when deploying |
| workload-identity-audience | Yes                            | Audience of the workload identity     |

### Secrets

| key           | required | description                                      |
|---------------|----------|--------------------------------------------------|
| fcm-vapid-key | No       | (if used) VAPID Key for Firebase Cloud Messaging |