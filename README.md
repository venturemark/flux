# flux



### Suspend Reconciliation

For testing purposes locally the reconciliation of e.g. a git repository can be
suspended. That way the git commit for the deployed application can be managed
manually without having the flux controllers overwriting changes made in the CRs
in the Kubernetes cluster.

```
flux -n infra suspend source chart infra-apiserver
```

Once suspended the associated helm release CR can be updated with the desired
git commit.

```
k -n infra edit helmreleases.helm.toolkit.fluxcd.io apiserver
```
