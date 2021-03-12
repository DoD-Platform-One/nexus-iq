# Sonatype Nexus IQ

Monitoring and notifications of open source vulnerabilities

This chart was sourced from
[Sonatype's Helm Charts.](https://github.com/sonatype/helm3-charts) with
minimal changes.

## Prerequisites

- Kubernetes Cluster deployed
- Kubernetes config installed in ~/.kube/config
- Helm installed

## Iron Bank

You can `pull` the Iron Bank image [here](https://registry1.dso.mil/harbor/projects/3/repositories/sonatype%2Fnexus-iq-server%2Fnexus-iq-server) and view the container approval [here](https://ironbank.dso.mil/repomap/sonatype/nexus-iq-server).

## Helm

Please reference complete list of providable variables
[here](https://github.com/sonatype/helm3-charts/tree/master/charts/nexus-iq#chart-configuration-options)

```bash
git clone https://repo1.dso.mil/platform-one/big-bang/apps/third-party/nexus-iq.git
helm install nexus-iq chart
```
