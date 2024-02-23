[![.github/workflows/release.yml](https://github.com/banshee86vr/ephemeral-test-environment/actions/workflows/release.yml/badge.svg)](https://github.com/banshee86vr/ephemeral-test-environment/actions/workflows/release.yml) [![semantic-release: angular](https://img.shields.io/badge/semantic--release-conventional-e10079?logo=semantic-release)](https://github.com/semantic-release/semantic-release)

# Ephemeral test environments for CI workflows

You can read the article at:

- My portfolio website: <https://lucabertelli.consulting/en/blog/vcluster>
- On Medium: <https://medium.com/@bertelli.luca/ephemeral-test-environments-for-ci-workflows>

## How to use vCluster and Argo Workflow to manage ephemeral test environments

Project structure:

```text
.
├── argo-workflow
│   └── lang
└── hello-world-app
```

- `argo-workflow`: CI/CD pipeline templates
  - `lang`: ArgoWorkflow Templates for supported languages
- `hello-world-app` folder: Go Hello world application that prints a beautiful octopus 🐙 in ASCII code

Key highlights from the article include:

1. **vCluster Usage**: The article introduces vCluster as a pivotal tool for creating lightweight, ephemeral Kubernetes clusters. It's interesting how vCluster can be employed to instantiate and manage test environments on-demand, covering the scenarios where temporary clusters are essential for testing.

2. **Argo Workflow Implementation**: The article delves into the integration of Argo Workflow, a workflow engine for Kubernetes, providing a way to configure the orchestration of the deployment, testing, and teardown processes efficiently. The tool also enables the final user to define another kind of process drawing DAGs (<https://argoproj.github.io/argo-workflows/walk-through/dag/>). This feature supports complex scenarios where there is a requirement to maximize parallelism when running tasks.
