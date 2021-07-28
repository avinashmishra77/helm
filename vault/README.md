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

```bash
helm template vault vault
```

### Install Helm chart

```bash
helm install vault vault
```
