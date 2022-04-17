# Bnkr Kubernetes Helm Chart

This Helm chart install [BNKR](https://bnkr.is).

## Get Repo Info

```console
helm repo add bnkr https://charts.bnkr.is
helm repo update
```

_See [helm repo](https://helm.sh/docs/helm/helm_repo/) for command documentation._

## Install Chart

```console
# Helm 3
$ helm install [RELEASE_NAME] bnkr/bnkr [flags]
```

_You can use `--render-subchart-notes` flag to render the PostgreSQL chart notes_

_See [helm install](https://helm.sh/docs/helm/helm_install/) for command documentation._

## Uninstall Chart

```console
# Helm 3
$ helm uninstall [RELEASE_NAME]
```

This removes all the Kubernetes components associated with the chart and deletes the release.
If you enabled the `PostgreSQL` section of the chart then you have to manually delete the PVC of the database.

_See [helm uninstall](https://helm.sh/docs/helm/helm_uninstall/) for command documentation._

## Upgrade Chart

```console
# Helm 3
$ helm upgrade [RELEASE_NAME] bnkr/bnkr [flags]
```

_You can use `--render-subchart-notes` flag to render the PostgreSQL chart notes_

_See [helm upgrade](https://helm.sh/docs/helm/helm_upgrade/) for command documentation._

## PostgreSQL

When you enable `postgresql` it uses [PostgreSQL packaged by Bitnami](https://artifacthub.io/packages/helm/bitnami/postgresql/11.1.19) behind the scenes, feel free to pass values to that chart in the `postgresql` section of your values file.

Bnkr consumes its required database values from the `postgresql.global` key.

