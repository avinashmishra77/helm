# Vault Helm Chart

## Create Chart

```bash
helm create vault
```

Helm deploys a default application in the template directory with a couple of examples. To convert this into a Helm Chart that we can use, we can clean up the directory and delete stuff we don't need.

* Delete the tests directory
* Delete everything except the _helpers.tpl
* Delete everything from within the values file

**Note**: </br>
Using the existing yaml files for the Vault setup and copied it into the templates folder.

### Test if the Chart renders correctly

From the helm folder, (**helm template \<deployment-name> \<chart-name>**) execute:

```bash
helm template vault vault
```

### Install Helm Chart

From the helm folder, (**helm install \<deployment-name> \<chart-name>**) execute:

```bash
helm install vault vault
```

To install into a specific namespace, (**helm install \<deployment-name> --namespace \<namespace> --create-namespace \<chart-directory>**), execute: 

```bash
helm install myvault --namespace vault-dev --create-namespace ./vault
```

### View installed Helm Charts

To list all charts (**helm list -A**), execute:
```bash
helm ls -A
```

To list chart in a specific namespace (**helm list --namespace \<namespace>**), execute:

```bash
helm ls --namespace <namespace>
```

### Uninstall Helm Charts

To uninstall chart (**helm uninstall \<deployment-name> --namespace \<namespace>**), execute:

```bash
helm uninstall myvault --namespace vault-dev
```
