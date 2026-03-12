# rhpds.quarkus_on_openshift

Ansible collection for Quarkus on OpenShift automation.

## Installation

Add to your `requirements.yml`:

```yaml
collections:
  - name: rhpds.quarkus_on_openshift
    source: https://github.com/rhpds/quarkus-on-openshift-automation.git
    type: git
```

Then install:

```bash
ansible-galaxy collection install -r requirements.yml
```

## Roles

### bootstrap_cluster

Bootstraps an OpenShift cluster for Quarkus workloads.

```yaml
- hosts: localhost
  roles:
    - role: rhpds.quarkus_on_openshift.bootstrap_cluster
      quarkus_on_openshift_bootstrap_cluster_ocp_ingress_domain: apps.example.com
      quarkus_on_openshift_bootstrap_cluster_ocp_api_url: https://api.example.com:6443
      quarkus_on_openshift_bootstrap_cluster_ocp_api_token: sha256~xxxxx
```

#### Variables

| Variable | Default | Description |
|---|---|---|
| `quarkus_on_openshift_bootstrap_cluster_ocp_ingress_domain` | `""` | OpenShift ingress domain |
| `quarkus_on_openshift_bootstrap_cluster_ocp_api_url` | `""` | OpenShift API URL |
| `quarkus_on_openshift_bootstrap_cluster_ocp_api_token` | `""` | OpenShift API token |
