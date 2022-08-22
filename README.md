# gitops-app-of-apps
This is an example to setup app an apps pattern for ArgoCD.

```sh
helm dependency update ./root-application
```

```sh
helm install --dry-run --debug root-application ./root-application/
```

```sh
helm install root-application ./root-application
```

```sh
helm uninstall root-application ./root-application
```
