# fibs-app-config
Kubernetes helm chart for deploying fibs-app docker images

This repo holds the helm chart for the [fibs-app](https://github.com/xianfengyuan/fibs-app).
The git action in [fibs-app](https://github.com/xianfengyuan/fibs-app) repo would update the following content in [values.yaml](https://github.com/xianfengyuan/fibs-app-config/blob/main/helm/fibs-app/values.yaml) file:

- image:
  -   repository: xianfengyuan/fibs-app
  -   pullPolicy: IfNotPresent
  -   . Overrides the image tag whose default is the chart appVersion.
  -   tag: 1b4107fc9cb310ca05170631b2f807d3bbdf35d1

This Helm chart includes Kubernetes HPA definition which can autoscale the cluster based on
 the targetCPUUtilizationPercentage or targetMemoryUtilizationPercentage parameters.

The Helm chart also defines the livenessProbe/readinessProbe to monitor the health of the pods
 on the cluster.
