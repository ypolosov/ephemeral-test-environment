[![.github/workflows/release.yml](https://github.com/banshee86vr/ephemeral-test-environment/actions/workflows/release.yml/badge.svg)](https://github.com/banshee86vr/ephemeral-test-environment/actions/workflows/release.yml) [![semantic-release: angular](https://img.shields.io/badge/semantic--release-conventional-e10079?logo=semantic-release)](https://github.com/semantic-release/semantic-release)

# Ephemeral test environments for CI workflows

You can read the article at:

- On my personal portfolio website: <https://lucabertelli.consulting/en/blog/vcluster>
- On Medium: <https://medium.com/@bertelli.luca/ephemeral-test-environments-for-ci-workflows>

## How to use vCluster, ArgoCD Events and Argo Workflow to manage short-live test ephemeral environments

Project structure:

```text
.
├── argo
│   ├── events
│   └── workflow
│       └── lang
├── hello-world-app
└── vcluster
```

- `argo` folder: All configurations made for
  - `events`: Argo Events webhook, trigger (for Argo Workflow), and sensor
  - `workflow`: CI/CD pipeline triggered by Argo Events
    - `lang`: ArgoWorkflow Templates for supported languages
- `hello-world-app` folder: Go Hello world application that prints a beautiful octopus 🐙 in ASCII code
- `vcluster` folder: All configurations made for creating VCluster where deploy the hello world application

Key highlights from the article include:

1. **vCluster Usage**: The article introduces vCluster as a pivotal tool for creating lightweight, ephemeral Kubernetes clusters. It's so interesting how vCluster can be employed to instantiate and manage test environments on-demand, covering the scenarios where temporary clusters are essential for testing purposes.

2. **Argo Events Integration**: The article explores the integration of Argo Events, a tool designed for event-driven architecture in Kubernetes. It details how Argo Events can be utilized to trigger and manage events received from the SCM to manage the lifecycle of short-lived test environments. This allows for dynamic and automated responses to changes in the testing and security requirements.

3. **Argo Workflow Implementation**: The article delves into the integration of Argo Workflow, a workflow engine for Kubernetes. It provides insights into how Argo Workflow can be configured to orchestrate the deployment, testing, and teardown processes efficiently. The tool enables the final user to define also another kind of process drawing DAGs (<https://argoproj.github.io/argo-workflows/walk-through/dag/>). This feature supports complex scenarios where there is a requirement to maximize parallelism when running tasks.
