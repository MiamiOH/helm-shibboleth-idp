# helm-template

The chart source can be found here: https://github.com/miamioh/helm-shibboleth-idp

## TL;DR

```console
helm install miamioh/helm-shibboleth-idp
```

## Introduction

This helm chart was based on one written by [Penn State Engineering](https://staging.artifacthub.io/packages/search?repo=psu-swe) discovered on [ArtifactHub](https://staging.artifacthub.io/packages/helm/psu-swe/shib-idp)

## Installing the Chart

To install the chart with the release name `my-release`:

```console
helm install miamioh/helm-shibboleth-idp --name my-release
```

The command deploys helm stuff in the default configuration. The [configuration](#configuration) section lists the parameters that can be configured during installation.

## Uninstalling the Chart

To uninstall/delete the `my-release` deployment:

```console
helm delete my-release
```

The command removes all the helm stuff associated with the chart and deletes the release.

## Configuration

The following table lists the configurable parameters of the heml-template chart and their default values.

| Parameter                           | Description                                                                                                            | Default            |
| ----------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ------------------ |
| `image.repository`                  | Repository for container image                                                                                         | `tier/shib-idp`    |
| `image.tag`                         | Image tag                                                                                                              | `4.1.0_20210324`   |
| `image.pullPolicy`                  | Pull policy                                                                                                            | `Always`           |
| `imagePullSecrets`                  |                                                                                                                        | `[]`               |
| `nameOverride`                      |                                                                                                                        | ``                 |
| `fullnameOverride`                  |                                                                                                                        | ``                 |
| `replicaCount`                      |                                                                                                                        | 1                  |
| `ingress.enabled`                   |                                                                                                                        | `true`             |
| `ingress.hosts`                     |                                                                                                                        | `[shib-idp.local]` |
| `ingress.annotations`               |                                                                                                                        | `{}`               |
| `ingress.tls`                       |                                                                                                                        | `{}`               |
| `preStopDelay`                      |                                                                                                                        | 60                 |
| `serviceAccount.create`             | Specifies whether a service account should be created                                                                  | `true`             |
| `serviceAccount.annotations`        | Annotations to add to the service account                                                                              | {}                 |
| `serviceAccount.name`               | The name of the service account to use. If not set and create is true, a name is generated using the fullname template | ``                 |
| `podSecurityContext.runAsUser`      |                                                                                                                        | 1000               |
| `securityContext.capabilities.drop` |                                                                                                                        | `[ALL]`            |
| `securityContext.runAsNonRoot`      |                                                                                                                        | true               |
| `securityContext.runAsUser`         |                                                                                                                        | 1000               |
| `resources.limits.cpu`              |                                                                                                                        | 2000m              |
| `resources.limits.memory`           |                                                                                                                        | 4Gi                |
| `resources.requests.cpu`            |                                                                                                                        | 1000m              |
| `resources.requests.memory`         |                                                                                                                        | 3Gi                |
| `initResources.limits.cpu`          |                                                                                                                        | 20m                |
| `initResources.limits.memory`       |                                                                                                                        | 50Mi               |
| `initResources.requests.cpu`        |                                                                                                                        | 10m                |
| `initResources.requests.memory`     |                                                                                                                        | 10Mi               |
| `nodeSelector`                      |                                                                                                                        | {}                 |
| `tolerations`                       |                                                                                                                        | []                 |
| `affinity`                          |                                                                                                                        | {}                 |

<!--
# Shibboleth IdP configuration
conf:
  # configmaps to be mounted under conf/ as files
  configMaps: {}
  sealedSecrets: {}
    # attribute-resolver.xml: nameOfconfigMapOrsecret

  # contents to be mounted under conf/ as files
  values: {}
    # some-file.xml: |
    #   file contents
    #   on multiple lines

  # data-only container with conf/ files located under /conf
  image: {}
    # repository: "nexus.ci.psu.edu:5000/docker/shib-idp-conf"
    # tag: "1.0"
    # pullPolicy: Always

metadata:
  image: {}

properties:
  # configmaps and secrets whose keys will be appended to conf/idp.properties on startup
  # keys are converted if necessary:
  #  IDP_BAR -> idp.bar
  configMaps: {}
  sealedSecrets: {}

  # raw properties to be appended to conf/idp.properties
  values: {}

credentials:
  # configmaps and secrets whose keys will be mounted under credentials/ as files
  configMaps: {}
  sealedSecrets: {}
  values: {}
   -->

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`. For example,

```console
helm install miamioh/helm-shibboleth-idp --name my-release \
  --set=image.repository=my-image
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart. For example,

```console
helm install miamioh/helm-shibboleth-idp --name my-release -f values.yaml
```

> **Tip**: You can use the default [values.yaml](values.yaml)
