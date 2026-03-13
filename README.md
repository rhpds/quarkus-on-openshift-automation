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
      quarkus_on_openshift_bootstrap_cluster_myvar: myvalue
```

#### Variables

| Variable | Default | Description |
|---|---|---|
| `quarkus_on_openshift_bootstrap_cluster_myvar` | `""` | Example variable |

### bootstrap_tenant

Bootstraps a tenant (user) on an OpenShift cluster.

```yaml
- hosts: localhost
  roles:
    - role: rhpds.quarkus_on_openshift.bootstrap_tenant
      quarkus_on_openshift_bootstrap_tenant_username: user1
      quarkus_on_openshift_bootstrap_tenant_user_password: changeme
      quarkus_on_openshift_bootstrap_tenant_namespaces:
        - user1-dev
        - user1-stage
```

#### Variables

| Variable | Default | Description |
|---|---|---|
| `quarkus_on_openshift_bootstrap_tenant_username` | `""` | Tenant username |
| `quarkus_on_openshift_bootstrap_tenant_user_password` | `""` | Tenant user password |
| `quarkus_on_openshift_bootstrap_tenant_namespaces` | `[]` | List of namespaces for the tenant |
