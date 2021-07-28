# Helm

## Installing Helm

Go to the [Helm github repo](https://github.com/helm/helm) and download and install the latest release (3.6.2).

```bash
curl -LO https://get.helm.sh/helm-v3.6.2-linux-amd64.tar.gz

tar -C /tmp/ -zxvf helm-v3.6.2-linux-amd64.tar.gz

rm -rf helm-v3.6.2-linux-amd64.tar.gz

mv /tmp/linux-amd64/helm /usr/local/bin/helm

chmod +x /usr/local/bin/helm

helm version
```

## A Starter Chart

This creates a shell chart structure that we can modify to suit our needs. Helm installs a default application to use as an example.

```bash
helm create <chart-name>
```

### The Chart File Structure

A chart is organized as a collection of files inside of a directory. The **directory name is the name of the chart** (without versioning information).

The basic structure looks like:

File(s)   | Descritption
--------  | ------------ 
Chart.yaml | A YAML file containing information about the chart
vaules.yaml | The default configuration values for this chart
templates (folder) | A directory of templates that, when combined with values, will generate valid Kubernetes manifests files.
charts (folder) | A directory containing other charts (subcharts).

* The "templates/" directory is for template files. When Helm evaluates a chart, it will send all of the files in the "templates/" directory through the template rendering enging. It then collects the results of those templates and sends them through on to Kubernetes.

* The "vaules.yaml" contains the default values for a chart. These values may be overridden by users during "helm install" or "helm upgrade".
  * we can have multiple values.yaml files either per microservice or per environment.

* The "Chart.yaml" file contains a description of the chart. You can acces it from within a template. The "charts/" directory may contain other charts (which we call subcharts).

**Note**: To quickly set up a chart, we can move our existing yamls files into the "templates" folder.