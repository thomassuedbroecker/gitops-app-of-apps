# gitops-app-of-apps

This is an example to setup app an apps pattern for ArgoCD.

## Configure Argo CD to use the `app of apps` pattern

First we will deploy the Argo CD `root-application` with the related project and repository to `Argo CD`.

* Update Helm dependencies

```sh
helm dependency update ./root-application
```

* Verify Helm configuration

```sh
helm install --dry-run --debug root-application ./root-application/
```

* Install Argo CD configuration using Helm

```sh
helm install root-application ./root-application
```

* Uninstall Argo CD configuration using Helm

```sh
helm uninstall root-application ./root-application
```
