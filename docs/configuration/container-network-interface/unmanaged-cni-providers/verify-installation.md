# Verify CNI plugin installation

Upon successful installation or upgrade of the CNI plugin, all MKE 4k
components will have a ``Running`` status.

To review the status of the Kubernetes components:

```bash
/usr/local/k0s/kc get pods -n kube-system -o wide
```
Example output:

