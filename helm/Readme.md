## Helm

Package manager

## Install helm using Brew

brew install helm

```
# creating the helm
helm create apache-helm

## install tree
brew install tree

## after changing the value 
helm package .


helm install dev-apache apache-helm
helm uninstall dev-apache

helm install dev-apache apache-helm -n dev-apache --create-namespace

helm upgrade prd-apache apache-helm 
```
