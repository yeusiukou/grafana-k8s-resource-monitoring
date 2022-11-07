# Kubernetes resource monitoring Grafana dashboard
[![license](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/instrumentisto/grafana-dashboard-kubernetes-prometheus/blob/master/LICENSE.md)
[![prometheus](https://img.shields.io/badge/prometheus-%5E15.18.0-green.svg)](https://github.com/prometheus/prometheus)
[![grafana](https://img.shields.io/badge/grafana-%5E9.2.3-green.svg)](https://github.com/grafana/grafana)

The dashboard offers a simple view of the resource consumption of the deployed pods and their impact on the cluster. The outline of requests and limits for each pod and their totals can be used as a tool to determine appropriate resource quotas for your cluster.

### Prerequisites
[Kubernetes](http://kubernetes.io/) cluster with deployed [Prometheus](https://prometheus.io/). Prometheus will use metrics provided by:
- [cAdvisor](https://github.com/google/cadvisor) (runs on each node by default)
- node-exporter, kube-state-metrics - can be installed with Prometheus via the [helm chart](https://github.com/prometheus-community/helm-charts/tree/main/charts/prometheus). Managed Kubernetes clusters such as AKS can have them enabled [automatically](https://learn.microsoft.com/en-us/azure/azure-monitor/essentials/prometheus-metrics-scrape-default).

### Features
- List of cluster nodes and their resources: CPU, memory, filesystem.
![CleanShot 2022-11-07 at 12 32 38](https://user-images.githubusercontent.com/8567013/200406399-96fbd65f-39ea-48af-a8ec-2b06bbf476d9.png)
- List of the pods restarted in the selected timeframe (hover over the dots to see the exact time of the restart).
- Counts of pods in each state.
![CleanShot 2022-11-07 at 11 57 00](https://user-images.githubusercontent.com/8567013/200406541-f4c98d38-ede8-44db-954a-0d016fcdf9db.png)
- Resource outline for each pod. Includes requests, limits and current usage stats. These metrics and the ability to filter by namespace can help calculate appropriate resource quotas for your cluster. Click on the magnifying glass to filter the dashboard by namespace, node or pod.
![CleanShot 2022-11-07 at 12 09 09](https://user-images.githubusercontent.com/8567013/200406603-7153d3cd-6f92-4415-92b4-ffeb1cd55426.png)
- Pod CPU and memory usage over time.
![CleanShot 2022-11-07 at 12 13 09](https://user-images.githubusercontent.com/8567013/200406615-2a2fd231-de0d-4a10-bbfc-94a5a4338d68.png)
