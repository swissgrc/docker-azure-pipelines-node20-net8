# Docker image for running Node.js commands in an Azure Pipelines container job

<!-- markdownlint-disable MD013 -->
[![License](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](https://github.com/swissgrc/docker-azure-pipelines-node20-net8/blob/main/LICENSE) [![Build](https://img.shields.io/github/actions/workflow/status/swissgrc/docker-azure-pipelines-node20-net8/publish.yml?branch=develop&style=flat-square)](https://github.com/swissgrc/docker-azure-pipelines-node20-net8/actions/workflows/publish.yml) [![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=swissgrc_docker-azure-pipelines-node20-net8&metric=alert_status)](https://sonarcloud.io/summary/new_code?id=swissgrc_docker-azure-pipelines-node20-net8) [![Pulls](https://img.shields.io/docker/pulls/swissgrc/azure-pipelines-node.svg?style=flat-square)](https://hub.docker.com/r/swissgrc/azure-pipelines-node) [![Stars](https://img.shields.io/docker/stars/swissgrc/azure-pipelines-node.svg?style=flat-square)](https://hub.docker.com/r/swissgrc/azure-pipelines-node)
<!-- markdownlint-restore -->

Docker image to run Node.js commands in [Azure Pipelines container jobs].

## Usage

This image can be used to run Node.js commands in [Azure Pipelines container jobs].

The following software is additionally available in the image:

| Software   | Included since |
|------------|----------------|
| Docker CLI | 20.10.0        |
| Git        | 20.10.0        |
| .NET 8     | 20.10.0        |

### Azure Pipelines Container Job

To use the image in an Azure Pipelines Container Job, add one of the following example tasks and use it with the `container` property.

The following example shows the container used for a deployment step with a Azure CLI command:

```yaml
  - stage: deploy
    jobs:
      - deployment: runAzureCLI
        container: swissgrc/azure-pipelines-node:latest-20-net8
        environment: smarthotel-dev
        strategy:
          runOnce:
            deploy:
              steps:
                - bash: |
                    node --version
```

### Tags

| Tag              | Description                                                                                         | Base Image                                | Node.js | Yarn    | Size                                                                                                                                  |
|------------------|-----------------------------------------------------------------------------------------------------|-------------------------------------------|---------|---------|---------------------------------------------------------------------------------------------------------------------------------------|
| latest-20-net8   | Latest stable release (from `main` branch)                                                          | swissgrc/azure-pipelines-dotnet:8.0.404   | 20.18.1 | 1.22.22 | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-node/latest-20-net8?style=flat-square)   |
| unstable-20-net8 | Latest unstable release (from `develop` branch)                                                     | swissgrc/azure-pipelines-dotnet:8.0.405   | 20.18.1 | 1.22.22 | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-node/unstable-20-net8?style=flat-square) |
| 20.10.0-net8     | [Node.js 20.10.0](https://github.com/nodejs/node/blob/main/doc/changelogs/CHANGELOG_V20.md#20.10.0) | swissgrc/azure-pipelines-dotnet:8.0.100   | 20.10.0 | 1.22.21 | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-node/20.10.0-net8?style=flat-square)     |
| 20.11.0-net8     | [Node.js 20.11.0](https://github.com/nodejs/node/blob/main/doc/changelogs/CHANGELOG_V20.md#20.11.0) | swissgrc/azure-pipelines-dotnet:8.0.101   | 20.11.0 | 1.22.21 | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-node/20.11.0-net8?style=flat-square)     |
| 20.11.1-net8     | [Node.js 20.11.1](https://github.com/nodejs/node/blob/main/doc/changelogs/CHANGELOG_V20.md#20.11.1) | swissgrc/azure-pipelines-dotnet:8.0.200   | 20.11.1 | 1.22.21 | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-node/20.11.1-net8?style=flat-square)     |
| 20.12.0-net8     | [Node.js 20.12.0](https://github.com/nodejs/node/blob/main/doc/changelogs/CHANGELOG_V20.md#20.12.0) | swissgrc/azure-pipelines-dotnet:8.0.202   | 20.12.0 | 1.22.22 | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-node/20.12.0-net8?style=flat-square)     |
| 20.12.1-net8     | [Node.js 20.12.1](https://github.com/nodejs/node/blob/main/doc/changelogs/CHANGELOG_V20.md#20.12.1) | swissgrc/azure-pipelines-dotnet:8.0.203   | 20.12.1 | 1.22.22 | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-node/20.12.1-net8?style=flat-square)     |
| 20.12.2-net8     | [Node.js 20.12.2](https://github.com/nodejs/node/blob/main/doc/changelogs/CHANGELOG_V20.md#20.12.2) | swissgrc/azure-pipelines-dotnet:8.0.204   | 20.12.2 | 1.22.22 | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-node/20.12.2-net8?style=flat-square)     |
| 20.13.0-net8     | [Node.js 20.13.0](https://github.com/nodejs/node/blob/main/doc/changelogs/CHANGELOG_V20.md#20.13.0) | swissgrc/azure-pipelines-dotnet:8.0.204   | 20.13.0 | 1.22.22 | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-node/20.13.0-net8?style=flat-square)     |
| 20.13.1-net8     | [Node.js 20.13.1](https://github.com/nodejs/node/blob/main/doc/changelogs/CHANGELOG_V20.md#20.13.1) | swissgrc/azure-pipelines-dotnet:8.0.300   | 20.13.1 | 1.22.22 | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-node/20.13.1-net8?style=flat-square)     |
| 20.14.0-net8     | [Node.js 20.14.0](https://github.com/nodejs/node/blob/main/doc/changelogs/CHANGELOG_V20.md#20.14.0) | swissgrc/azure-pipelines-dotnet:8.0.301   | 20.14.0 | 1.22.22 | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-node/20.14.0-net8?style=flat-square)     |
| 20.15.0-net8     | [Node.js 20.15.0](https://github.com/nodejs/node/blob/main/doc/changelogs/CHANGELOG_V20.md#20.15.0) | swissgrc/azure-pipelines-dotnet:8.0.301   | 20.15.0 | 1.22.22 | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-node/20.15.0-net8?style=flat-square)     |
| 20.15.1-net8     | [Node.js 20.15.1](https://github.com/nodejs/node/blob/main/doc/changelogs/CHANGELOG_V20.md#20.15.1) | swissgrc/azure-pipelines-dotnet:8.0.301   | 20.15.1 | 1.22.22 | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-node/20.15.1-net8?style=flat-square)     |
| 20.16.0-net8     | [Node.js 20.16.0](https://github.com/nodejs/node/blob/main/doc/changelogs/CHANGELOG_V20.md#20.16.0) | swissgrc/azure-pipelines-dotnet:8.0.303   | 20.16.0 | 1.22.22 | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-node/20.16.0-net8?style=flat-square)     |
| 20.17.0-net8     | [Node.js 20.17.0](https://github.com/nodejs/node/blob/main/doc/changelogs/CHANGELOG_V20.md#20.17.0) | swissgrc/azure-pipelines-dotnet:8.0.401   | 20.17.0 | 1.22.22 | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-node/20.17.0-net8?style=flat-square)     |
| 20.18.0-net8     | [Node.js 20.18.0](https://github.com/nodejs/node/blob/main/doc/changelogs/CHANGELOG_V20.md#20.18.0) | swissgrc/azure-pipelines-dotnet:8.0.402   | 20.18.0 | 1.22.22 | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-node/20.18.0-net8?style=flat-square)     |
| 20.18.1-net8     | [Node.js 20.18.1](https://github.com/nodejs/node/blob/main/doc/changelogs/CHANGELOG_V20.md#20.18.1) | swissgrc/azure-pipelines-dotnet:8.0.404   | 20.18.1 | 1.22.22 | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-node/20.18.1-net8?style=flat-square)     |

[Azure Pipelines container jobs]: https://docs.microsoft.com/en-us/azure/devops/pipelines/process/container-phases
