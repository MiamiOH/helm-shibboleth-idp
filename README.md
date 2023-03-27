# helm-template

The chart source can be found here: https://github.com/miamioh/helm-shibboleth-idp

## TL;DR

```console
helm install miamioh/helm-shibboleth-idp
```

## Introduction

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

| Parameter          | Description                    | Default                                 |
| ------------------ | ------------------------------ | --------------------------------------- |
| `image.repository` | Repository for container image | `k8s.gcr.io/kubernetes-dashboard-amd64` |
| `image.tag`        | Image tag service              | `false`                                 |

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
