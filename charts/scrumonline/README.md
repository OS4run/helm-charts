# ScrumOnline

[![Gitter](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/scrumonline/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

PHP web app for planning poker. It includes a master view for the ScrumMaster and a simple responsive card view for the team. A deployed demo is available at http://www.scrumpoker.online

## Source software
[Original Project - https://github.com/Toxantron/scrumonline](https://github.com/Toxantron/scrumonline)

[Docker project - https://github.com/chrisns/scrumonline](https://github.com/chrisns/scrumonline)


## Prerequisites

* Kubernetes >= 1.9

## Installing the repository
```bash
$ helm repo add os4run https://os4run.github.io/helm-charts/
```

## Installing the Chart

To install the chart with the release name `my-release`:

```bash
$ helm install --namespace default --name my-release os4run/scrumonline
```

The command deploys a deployment for scrum poker planning website. The [configuration](#configuration) section lists the parameters that can be configured during installation.

## Uninstalling the Chart

To uninstall/delete the `my-release` deployment:

```bash
$ helm delete [--purge] my-release
```

The command removes all the Kubernetes components associated with the chart and deletes the release.

## Using scrumonline

Configure ingress to access the website or make it available through port forwarding.

## Configuration

| Parameter                     | Description                                                                | Default                                     |
|------------------------------:|:---------------------------------------------------------------------------|:--------------------------------------------|
| **image.repository**         | `true` the image to be used                       | `chrisns/scrumonline`                                      |
| **image.pullPolicy**               | the pullPolicy which should be used                                 | `IfNotPresent`                                      |
| **service.type**           | The service type                               | `ClusterIP`                                     |
| **service.port**     |  The service port                          | `80`                                      |
| **ingress.enabled**                | Enable ingress resource      | `false`                      |
| **ingress.host**                 | The ingress host FQDN                                             | `scrumonline.local`                                   |
| **ingress.scheme**          | The scheme used to access the website                                 | `https`                              |
| **resources**                 | CPU/Memory resource requests/limits                                        | `{}`                                        |


## Contribute
If you want to contribute you can just clone the repository and follow the deployment instructions. Any changes must be commited to a fork and then merged by issuing a pull request. 


## Todo
* External database and persistence
