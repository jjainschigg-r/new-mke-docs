# Scaling Guidelines

The method for scaling KOF depends on the type of expansion:

## Regional Expansion

1. Deploy a [regional cluster](./kof-install.md#regional-cluster) in the new region.
2. Configure child clusters in this region to point to this regional cluster.

## Adding a New Child Cluster

1. Apply templates, as in the [child cluster](./kof-install.md#child-cluster) section.
2. Verify the data flow.
3. Configure any custom dashboards.

## You Must Construct Additional Pylons

1. Change the `replicaCount` of components like `victoria-logs-cluster`
    as documented in the [regional cluster](./kof-install.md#regional-cluster) section.
2. Change the `replicas` number of components like `opencost`
    as documented in the [child cluster](./kof-install.md#child-cluster) section.
