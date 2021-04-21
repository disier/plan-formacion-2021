# Day 3

## Git Hub pages

1. Read introduction
2. Create main github Page
  1. Learn how to change Title and subtitle
  2. Learn that commits takes a couple of minutes to display on (https://disier.github.io/plan-formacion-2021/)
  3. Read [Mastewring Markdown](https://guides.github.com/features/mastering-markdown/)
  4. Learn how to create [Relative Links](https://github.blog/2016-12-05-relative-links-for-github-pages/)
3. Create separate pages for [Day 1](day1.md) and [Day 2](day2.md)

## Automatic deploy to Azure Blob Storage

1. Read [Set up a GitHub Actions workflow to deploy your static website in Azure Storage](https://docs.microsoft.com/es-es/azure/storage/blobs/storage-blobs-static-site-github-actions)
2. Generate Deployment credentials

  `az ad sp create-for-rbac --name blamarkwebstorage --role contributor --scopes /subscriptions/486c4daa-77bd-41bc-a27b-a0afc68c6c32/resourceGroups/BlaumarkWebTest --sdk-auth`

  The generated credential is:

  ```json
{
  "clientId": "ed6dfa5d-064f-42f3-9034-87c0ce65bd78",
  "clientSecret": "BIzFlqNjlT96fk~FfA2Nu~FCpdLbzjCb95",
  "subscriptionId": "486c4daa-77bd-41bc-a27b-a0afc68c6c32",
  "tenantId": "dbf94a9d-4528-4958-b6cb-7a1201ed5da1",
  "activeDirectoryEndpointUrl": "https://login.microsoftonline.com",
  "resourceManagerEndpointUrl": "https://management.azure.com/",
  "activeDirectoryGraphResourceId": "https://graph.windows.net/",
  "sqlManagementEndpointUrl": "https://management.core.windows.net:8443/",
  "galleryEndpointUrl": "https://gallery.azure.com/",
  "managementEndpointUrl": "https://management.core.windows.net/"
}
```
3. Save AZURE_CREDENTIALS secret on repository
4. Create main.yml workflow on HitHub
5. Solve `Az CLI Login failed.` error
