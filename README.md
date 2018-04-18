# Helm chart for ACR autoupdate

Sample to show base image updates and multi-container helm deploy with ACR Build

This repo contains a simple 2 container app in the following model 


> Nginx-Ingress-Controller  <---> NodeJS webapp  <--->  DotnetCore Webapi App 


## Related repositories 

These are used to generate the web app and the API app. 

[AzureCR/acr-patch-sample-web](https://github.com/AzureCR/acr-patch-sample-web)

[AzureCR/acr-patch-sample-api](https://github.com/AzureCR/acr-patch-sample-api)


## Install instructions 

Once you obtain a read credential for the registry set the following variables 

|Variable|Description|
|--------|-----------|
| APP_HOST | DNS name that you want the web app to be bound to | 
| REGISTRY  | Registry host in the form name.azurecr.io |
| REGISTRY_USERNAME | The username used to login into the registry to pull the image |
| REGISTRY_PASSWORD | Password for the user above |


```bash
cd jenga
helm install jenga --set web.host=$APP_HOST --set imageCredentials.registry=$REGISTRY --set imageCredentials.username=$REGISTRY_USERNAME --set imageCredentials.password=$REGISTRY_PASSWORD .
```

TODO:
1. ~~Helm ingress [template](jenga/templates/webapp.yaml) uses a fixed host and requires parameterization.~~
2. ~~Move containers to registry and inject secrets~~
3. Make dotnet app read from other data sources