# Nexus Helm Charts Repository

## Directory Structure

This repository contains Helm charts for various data engineering services. Each service is organized into its own directory, which includes its specific Helm chart and Helmfile for deployment management in Kubernetes.

/nexus
  /airflow
    ├─ charts/
    ├─ values.yaml
    └─ Helmfile.yaml
  /dbt
    ├─ charts/
    ├─ values.yaml
    └─ Helmfile.yaml
  /spark
    ├─ charts/
    ├─ values.yaml
    └─ Helmfile.yaml
  /trino
    ├─ charts/
    ├─ values.yaml
    └─ Helmfile.yaml
  /hive
    ├─ charts/
    ├─ values.yaml
    └─ Helmfile.yaml


Each service directory contains:
- `charts/`: Contains the Helm chart files.
- `values.yaml`: Defines the configuration values for the Helm chart.
- `Helmfile.yaml`: Contains the Helmfile specifications for deploying the service.

## Usage Instructions

### Prerequisites

- A Kubernetes cluster
- Helm v3.x
- Helmfile

### Installing a Service

To install a service such as Airflow, navigate to the respective service directory and run:

```bash
cd nexus/airflow
helmfile apply
```

### Bumping the Version of a Release

To update the version of a Helm chart for a service:

  - Edit Helmfile.yaml.
  - Change the version key to the new chart version.
  - Save the file and apply the changes:

  `helmfile apply`

### Common Helmfile Commands

  - List all releases: helmfile -n <namespace> list
  - Destroy a release: helmfile -n <namespace> destroy