# Trigger Argo Workflow Pipelines with Argo Events

Folders structure:

```
.
├── events
│   └── README.md
└── workflow
    ├── README.md
    ├── ci.yaml
    ├── cd.yaml
    ├── images
    │   └── ...
    └── lang
        └── go.yaml
```

This CI/CD pipeline automates the build and deployment process for applications, focusing on a Dockerized GoLang application for this experiment. It consists of the following phases:

1. **Cloning Repository**: Fetches the source code from the git repository.
2. **Building Application**: Utilizes the GoLang template to compile the Go application.
3. **Building and Pushing Docker Image**: Packages the application into a Docker image and pushes it to the registry.
4. **Preparing an ephemeral environment**: Prepares an ephemeral environment using vCluster where the user can test the application inside an isolated Kubernetes cluster
5. **Deploy the application**: Deploy the application Helm chart on the vCluster just created

## Folder Structure
- `ci.yaml`: Argo Workflow Template for the Docker image build and push phases:
  1. Clone the git repository.
  2. Build the application using the GoLang template.
  3. Build and push the Docker image to the registry.
- `cd.yaml`: Argo Workflow Template for the deploy phases:
  1. Create a new vCluster
  2. Clone the repository with the application Helm chart
  3. Deploy on vCluster the application Helm chart
- `lang/go.yaml`: Argo Workflow Template to build Go applications.

## Introduction
This experiment provides an overview of Argo Workflow Pipelines and Argo Events, including their concepts, creation, configuration, and integration for effective workflow management and event-driven architecture.

### Argo Workflow Pipelines
Argo Workflows is an open-source container-native workflow engine for orchestrating parallel jobs on Kubernetes. It enables users to define complex workflows as code, automating and orchestrating tasks efficiently.

#### Key Concepts:
- **Workflow**: A directed acyclic graph (DAG) of tasks and dependencies, representing the workflow logic.
- **Steps**: Individual units of work within a workflow, typically containerized tasks.
- **Templates**: Reusable specifications for defining steps in workflows, allowing for modular and maintainable workflows.
- **Artifacts**: Data or files produced by steps within the workflow.
- **Parameters**: Inputs to templates or steps, allowing for dynamic workflow behavior.
- **Outputs**: Results produced by workflows, including artifacts and status information.

#### Creation and Configuration:
1. **Define Workflow**: Write YAML or JSON specifications defining the workflow, including steps, dependencies, inputs, and outputs.
2. **Configure Resources**: Specify Kubernetes resources required for workflow execution, such as containers, volumes, and environment variables.
3. **Handle Errors and Retries**: Implement error handling and retry mechanisms to ensure robustness and reliability.
4. **Customize Workflow Logic**: Utilize advanced features like loops, conditionals, and parameterization to create flexible workflows.
5. **Optimize Performance**: Fine-tune resource utilization, parallelism, and scheduling for optimal performance and resource efficiency.

### Argo Events
Argo Events extends Kubernetes with event-driven architecture capabilities, enabling users to trigger workflows and other actions in response to events within the Kubernetes ecosystem or external systems.

#### Key Concepts:
- **Event Sources**: Sources of events, including Kubernetes resources, messaging systems, webhooks, and custom triggers.
- **Event Types**: Different types of events, such as resource creation, updates, or custom events defined by users.
- **Event Sensors**: Components responsible for detecting and processing events, triggering associated actions.
- **Handlers**: Actions or workflows executed in response to events, such as invoking Argo Workflows pipelines.

#### Creation and Configuration:
1. **Define Event Sources**: Configure event sources to monitor for relevant events, specifying filters and event types.
2. **Set Up Event Sensors**: Deploy event sensors to detect events from configured sources and route them to appropriate handlers.
3. **Implement Handlers**: Define handlers to execute desired actions or workflows in response to detected events.
4. **Monitor and Debug**: Monitor event processing and troubleshoot issues using logs, metrics, and observability tools.
5. **Integrate with Workflows**: Integrate Argo Events with Argo Workflows pipelines to automate workflows based on detected events, enabling event-driven automation and orchestration.