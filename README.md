# Deployment von Logic Apps mit GitHub Actions

## Vorbereitungen
### 1. Anlegen eines Service Principal
```azurecli
az ad sp create-for-rbac --name <YOUR-SP-NAME> --role contributor --scopes /subscriptions/<YOUR-SUBSCRIPTION-ID>/resourceGroups/<YOUR-RESOURCE-GROUP> --sdk-auth
```
Den Output für den nächsten Schritt kopieren und als Secret Content unter 2. einfügen.

### 2. GitHub Secret Content anlegen

> GitHub Repository > Settings > Secrets and variables > Actions > New Repository secret

SecretName = __AZURE_CRENDTIALS__
```json
{
  "clientId": "<YOUR-CLIENT-ID>",
  "clientSecret": "<YOUR-CLIENT-SECRET>",
  "subscriptionId": "<YOUR-SUBSCRIPTION-ID>",
  "tenantId": "<YOUR-TENANT-ID>",
  "activeDirectoryEndpointUrl": "https://login.microsoft.com",
  "resourceManagerEndpointUrl": "https://management.azure.com/",
  "activeDirectoryGraphResourceId": "https://graph.windows.net/",
  "sqlManagementEndpointUrl": "https://management.core.windows.net:8443/",
  "galleryEndpointUrl": "https://gallery.azure.com/",
  "managementEndpointUrl": "https://management.core.windows.net/"
}
```
