# Helm chart for ACR autoupdate

Sample to show base image updates and multi-container helm deploy with ACR Build

This repo contains a simple 2 container app in the following model 


> Nginx-Ingress-Controller  <---> NodeJS webapp  <--->  DotnetCore Webapi App 


## Related repositories 

These are used to generate the web app and the API app. 

[AzureCR/acr-patch-sample-web](https://github.com/AzureCR/acr-patch-sample-web)

[AzureCR/acr-patch-sample-api](https://github.com/AzureCR/acr-patch-sample-api)

TODO:
1. Helm ingress [template](jenga/templates/webapp.yaml) uses a fixed host and requires parameterization. 
2. Move containers to registry and inject secrets
3. Make dotnet app read from other data sources


