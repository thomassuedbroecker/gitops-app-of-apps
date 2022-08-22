# gitops-app-of-apps

This is an example to setup app an apps pattern for ArgoCD.

Using the basic setup of the blog post from ["Use Software Everywhere and IasCable to setup GitOps on a Red Hat OpenShift Cluster in a Virtual Private Cloud on IBM Cloud"](https://wp.me/paelj4-1tZ).

That means:

* IBM Cloud is used
* Red Hat OpenShift in a VPC is setup
* Argo CD is setup and initial bootstap configured

But in that example we don't use the configured bootstap resoures for Argo CD `repository`, `project` and `application`. 

We setup our own `"app-of-apps"` root application.
We reuse the existing `"openshift-gitops"` workspace.

## Steps 1: Configure `Argo CD` to use own `app of apps` configuration

First we will deploy the Argo CD `root-application` with the related project and repository to `Argo CD`.

* Update Helm dependencies

```sh
helm dependency update ./root-application
```

* Verify Helm configuration

```sh
helm lint
helm install --dry-run --debug root-application ./root-application/
```

* Install Argo CD configuration using Helm

```sh
helm install root-application ./root-application/
```

* Uninstall Argo CD configuration using Helm

```sh
helm uninstall root-application
```
