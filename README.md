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
      quarkus_on_openshift_bootstrap_cluster: myvarvalue1
```

#### Variables

| Variable | Default | Description |
|---|---|---|
| `quarkus_on_openshift_bootstrap_cluster` | `""` | Value to pass to the bootstrap cluster role |
