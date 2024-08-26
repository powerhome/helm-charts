# Power Helm Charts
Helm charts created by Power Home Remodeling Group.

## Usage
You will need the [Helm Git](https://github.com/aslafy-z/helm-git) plugin installed:

```sh
helm3 plugin install https://github.com/aslafy-z/helm-git
```

If you are using [Helmfile](https://github.com/roboll/helmfile), you can add the following to your `Helmfile`:

```yaml
repositories:

  # This allows you to reference different chart versions created with different tags
  - name: powerhome-crunchydata-pgo
    url: git+https://github.com/powerhome/helm-charts@charts?ref=crunchydata-pgo-v0.2.4
  - name: powerhome-crunchydata-pgo-db
    url: git+https://github.com/powerhome/helm-charts@charts?ref=crunchydata-pgo-db-v0.2.4
  - name: powerhome-openldap
    url: git+https://github.com/powerhome/helm-charts@charts?ref=openldap-v1.3.0

  # This will reference the chart versions available for all charts on main
  - name: powerhome
    url: git+https://github.com/powerhome/helm-charts@charts?ref=main

releases:

  - name: my-database-pgo
    chart: powerhome-crunchydata-pgo/crunchydata-pgo
    namespace: my-namespace
    version: 0.2.4
    values: []

  - name: my-database-pgo-db
    chart: powerhome-crunchydata-pgo-db/crunchydata-pgo-db
    namespace: my-namespace
    version: 0.2.4
    values: []

  - name: openldap
    chart: powerhome-openldap/openldap
    namespace: my-namespace
    version: 1.3.0
    values: []
```
