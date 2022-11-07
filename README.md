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
- List of the pods restarted in the selected timeframe (hover over the dots to see the exact time of the restart).
- Counts of pods in each state.
- Resource outline for each pod. Includes requests, limits and current usage stats. These metrics and the ability to filter by namespace can help calculate appropriate resource quotas for your cluster. Click on the magnifying glass to filter the dashboard by namespace, node or pod.
- Pod CPU and memory usage over time.
