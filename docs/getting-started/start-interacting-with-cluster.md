# Start interacting with the cluster

To start interacting with the cluster, use `kubectl` with the `mke` context.
Though to do that, you need to specify the configuration. Use `mkectl` to output
the kubeconfig of the cluster to `~/mke/.mke.kubeconf`.

You can apply `.mke.kubeconf` using any one of the following methods:

- Set the `KUBECONFIG` environment variable to point to `~/.mke/mke.kubeconf`:

  ```bash
export KUBECONFIG=~/.mke/<cluster name>.kubeconfig
  ```
- Append the contents to the default kubeconfig:

  ```bash
cat ~/.mke/mke.kubeconf >> ~/.kube/config
  ```
- Specify the kubeconfig as a command argument:

  ```bash
kubectl --kubeconfig ~/.mke/mke.kubeconf
  ```
Example output:

```bash
$ kubectl --context mke get nodes

NAME    STATUS   ROLES           AGE   VERSION
node1   Ready    <none>          2d    v1.29.3+k0s
node2   Ready    control-plane   2d    v1.29.3+k0s
```
To modify the cluster configuration, edit the YAML configuration file and
rerun the `apply` command:

```bash
mkectl apply -f mke4.yaml
```