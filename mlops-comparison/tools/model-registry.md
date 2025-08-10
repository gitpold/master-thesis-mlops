# 37 Component - Model Registry

| Name | 37 Component - Model Registry | | | | | |
|------|------|------|------|------|------|------|
| Status | DRAFT | | | | | |
| **Context / Problem / Issue Description** | A key requirement of a machine learning project is a model registry to store models, manage versioning, and oversee the entire model lifecycle, from development to deployment. Here, we compare various model registry tools to ensure efficient model management and streamlined deployment processes. | | | | | |
| **Options considered** | Option A | Option B | Option C | Option D | Option E | Option F |
| Name & Link | [MLflow](https://mlflow.org/) Model Registry | [Kubeflow](https://www.kubeflow.org/) Model Registry | [Azure ML](https://azure.microsoft.com/en-us/products/machine-learning) Model Registry | [Databricks](https://www.databricks.com/) Model Registry | | |
| Description | Component of MLflow that provides a central repository to manage the lifecycle of machine learning models | Part of the Kubeflow ecosystem providing functionalities to manage and version models | Part of Azure ML | Part of Databricks (is basically a managed MLflow registry) | | |
| License & Cost | • Apache 2.0<br/>• free | • Apache 2.0<br/>• free | • proprietary<br/>• cost based on use of resources | • proprietary<br/>• cost based on use of resources | | |
| Documentation | https://mlflow.org/docs/latest/model-registry.html | https://www.kubeflow.org/docs/components/model-registry/ | https://learn.microsoft.com/en-us/azure/machine-learning/how-to-manage-registries?view=azureml-api-2&tabs=cli | https://docs.databricks.com/en/machine-learning/manage-model-lifecycle/workspace-model-registry.html | | |
| Infrastructure / How to run it | • can run on local machines, on-premise servers or cloud infrastructure | • Kubernetes | • managed service | • managed service | | |
| **Academia** | | | | | | |
| Advantages | | | | | | |
| Disadvantages | | | | | | |
| **Requirements** | | | | | | |
| Compatibility with Azure | ✅ | ✅ | ✅ | ✅ | | |
| Compatibility with GitHub | n.a. | n.a. | n.a. | n.a. | | |
| No own Kubernetes needed | ✅ | ❌ | ✅ | ✅ | | |
| | | | | | | |
| Allowed at Bosch | ✅ | ✅ | ✅ | ✅ | | |
| Supports all kinds of ML | ✅ | ❓ | ✅ | ❓ | | |
| Supports on-premise | ✅ | ✅ | ❌ | ❌ | | |
| | | | | | | |
| User Experience | • user friendly UI<br/>• good documentation<br/>• no multi-tenancy? | • Kubernetes expertise might be required/helpful | • good UI<br/>• integrated with Azure ML Studio | • user friendly UI<br/>• seamless integration with Databricks workspace | | |
| Maintainability | • large community support<br/>• maintenance effort probably depends on deployment method | • requires Kubernetes experience<br/>• can be complex to manage | • low maintenance effort (managed service) | • low maintenance effort (managed service) | | |
| Integration with CI/CD concept | • good integration via APIs | • integrated well with Kubeflow and Kubernetes based CI/CD (for example GitOps via Argo) | • integrates well with Azure DevOps and GitHub | • integrates well with Azure DevOps and GitHub | | |
| Reliability & Stability | • mature solution<br/>• stability might depend on deployment method | • reliable but complexity can introduce instability | • very reliable (managed service with SLAs) | • very reliable (managed service with SLAs) | | |
| Modularity & Reusability | • modular design | • modular (part of the Kubeflow ecosystem) | • modular, but highly integrated into the Azure ecosystem | • modular, but integrated within the Databricks ecosystem | | |
| Performance & Scalability | • probably depends on setup | • highly scalable with Kubernetes | • highly scalable via Azure cloud infrastructure | • highly scalable via cloud infrastructure<br/>• Apache Spark | | |
| | | | | | | |
| Tool already existing at Bosch | ✅ | ❌ | ✅ | ✅ | | |
| | | | | | | |
| **Decision** | Azure ML or Databricks Model Registry | | | | | |
| Justification | • either Azure ML or Databricks will be used as a base MLOps platform and provide both an integrated model registry so using them is the obvious choice | | | | | |
| Decided by | | | | | | |
| Date of decision | <[dd.mm](http://dd.mm).yyyy> | | | | | |
| Comments / Conditions to be met | <bullet point list, task tracking issues> | | | | | |
| Related Decisions | <link to related decision> | | | | | |
