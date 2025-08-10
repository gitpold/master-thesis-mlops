# 33 Component - Model Training Pipeline & Workflow Orchestration

Based on a rapid review of the white and grey literature on MLOps, the following tools were identified for the Model Training Pipeline & Workflow Orchestration category:

- Akira AI
- Apache Airflow
- Argo Workflows
- BodyWork
- Flyte
- Kedro
- Kubeflow Pipelines
- Prefect

Since this list of tools is too extensive for a comprehensive evaluation of all entries, the following evaluation is limited to a subset of popular or promising tools.
In addition, some corresponding components of the platforms (if existing) or tools proposed by other means (e.g. by team members) are included in the comparison.

| Name | 33 Component - Model Training Pipeline & Workflow Orchestration | | | | | | | |
|------|------|------|------|------|------|------|------|------|
| Status | DRAFT | | | | | | | |
| **Context / Problem / Issue Description** | An essential part of a machine learning project is orchestrating model training pipelines to ensure efficient and seamless workflow management. Tools for workflow orchestration automate the training process, support reproducibility, and enable scalability. Here, we compare various tools for model training pipeline and workflow orchestration to optimize and streamline ML development processes. | | | | | | | |
| **Options considered** | **Option A** | Option B | Option C | Option D | Option E | **Option F** | Option G | **Option H** |
| Name & Link | [Apache Airflow](https://airflow.apache.org/) | [Argo Workflows](https://argoproj.github.io/workflows/) | [Flyte](https://flyte.org/) | [Kedro](https://kedro.org/) | [Kubeflow](https://www.kubeflow.org/) Pipelines | [Prefect](https://www.prefect.io/) | [Azure ML](https://azure.microsoft.com/en-us/products/machine-learning) Jobs & Pipelines | [Databricks](https://www.databricks.com/) Jobs & Workflows |
| Description | A platform to programmatically author, schedule and monitor workflows | Kubernetes-native workflow engine supporting DAG and step-based workflows | Scalable and flexible workflow orchestration platform that seamlessly unifies data, ML and analytics stacks | Python framework to build production-ready data science pipelines | A platform for building then deploying portable and scalable machine learning workflows using Kubernetes | A workflow orchestration tool empowering developers to build, observe, and react to data pipelines | Job execution & Pipeline feature integrated into Azure ML platform | Job execution & Workflow feature integrated into Databricks platform |
| License & Cost | • Apache 2.0<br>• free | • Apache 2.0<br>• free | • Apache 2.0<br>• free<br>• manged cloud version with different pricing tiers | • Apache 2.0<br>• free | • Apache 2.0<br>• free | • Apache 2.0<br>• free<br>• manged cloud version with different pricing tiers | • enterprise<br>• pay per use | • open core<br>• pay per use |
| Documentation | https://airflow.apache.org/docs/ | https://argo-workflows.readthedocs.io/en/latest/ | https://docs.flyte.org/en/latest/ | https://docs.kedro.org/en/stable/ | https://www.kubeflow.org/docs/components/pipelines/v2/introduction/ | https://docs.prefect.io/latest/ | https://learn.microsoft.com/en-us/azure/machine-learning/concept-ml-pipelines?view=azureml-api-2 | https://docs.databricks.com/en/workflows/index.html |
| Infrastructure / How to run it | • can be deployed on local servers, on-premise or at a cloud provider<br>• supports deployment via Docker and to Kubernetes via Helm Chart<br>• needs a database | • needs Kubernetes cluster on-premise or at cloud provider<br>• Helm Chart available | • can be installed locally via PIP and run on developer machine<br>• needs Kubernetes cluster for deployment (on-premise or at cloud provider)<br>• needs a database | • can be run locally or via Docker on a server<br>• integrated with various orchestration tools (Airflow, Prefect, Azure ML Pipelines, Databricks, ...) | • need Kubernetes cluster<br>• integrates tightly with other Kubeflow components | • can be installed via PIP on local machine or server in the cloud<br>• deployment via Helm Chart to Kubernetes possible<br>• managed cloud version available | • managed service as part of Azure ML | • managed service as part of Databricks |
| **Academia** | | | | | | | | |
| Advantages | • easily integrated with GCP, AWS, Azure and many other platforms ¹<br>• user friendly web interface ²<br>• high flexibility ² | • based on YAML ²<br>• large community ²<br>• supports wide range of ecosystem (for example Kedro, Kubeflow, Seldon, ...) ²<br>• user interface to manage workflows ²<br>• scheduling via cron ² | • architecture prioritizes scalability and reproducibility ²<br>• multi-language support (Python, Java, Scala) ²<br>• UI ³<br>• lightweight ³<br>• scheduled workflows ³ | • helps teams establish collaboration standards ²<br>• focuses on reproducibility and maintainability ³<br>• UI ³<br>• lightweight ³ | • UI ¹<br>• utilizes Docker containers ¹ | • lightweight ⁴<br>• user-friendly dashboard ⁵ | | |
| Disadvantages | | | | | | | | |
| **Requirements** | | | | | | | | |
| Compatibility with Azure | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Compatibility with GitHub | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| No own Kubernetes needed | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ |
| | | | | | | | | |
| Allowed at Bosch | ✅ | ✅ | ✅<br>• no cloud onboarding info | ✅ | ✅ | ✅<br>• no cloud onboarding info | ✅ | ✅ |
| Supports all kinds of ML | ✅ | ✅ | ✅ | (✅) | ✅ | ✅ | ✅ | ✅ |
| Supports on-premise | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| | | | | | | | | |
| User Experience | • some learning curve | • requires Kubernetes & YAML knowledge | • simple UI | • simple UI | • requires Kubernetes knowledge | • simple, modern UI | • integrated with Azure ML platform<br>• provides visual approach for creating pipelines | • integrated with Databricks platform<br>• code-centric approach |
| Maintainability | • requires some setup and maintenance | • requires Kubernetes setup and maintenance | • easy to maintain<br>• but Kubernetes management needed | • easy to maintain | • requires Kubernetes setup and maintenance | • easy to maintain | • managed service, low maintenance effort | • managed service, low maintenance effort |
| Integration with CI/CD concept | • good CI/CD integration | • good CI/CD integration | • good CI/CD integration | • good CI/CD integration | • good CI/CD integration | • good CI/CD integration | • good CI/CD integration | • good CI/CD integration |
| Reliability & Stability | • reliable, mature | • reliable, stable Kubernetes integration | • reliable, strong community support | • reliable, growing community support | • reliable, mature | • reliable, strong community support | • reliable, enterprise | • reliable, enterprise |
| Modularity & Reusability | • modular, supports various workflows | • modular, integrates with Kubernetes | • modular, supports various workflows | • modular, supports various workflows | • modular, integrates with Kubernetes | • modular, supports various workflows | • not as modular, integrated with Azure ML platform | • not as modular, integrated with Datbricks platform |
| Performance & Scalability | • good performance, scalable | • high performance, scalable with Kubernetes | • high performance, scalable with Kubernetes | • good performance, scalable | • high performance, scalable with Kubernetes | • good performance, scalable | • good performance, scalable via Azure | • good performance, highly scalable via Spark |
| | | | | | | | | |
| Tool already existing at Bosch | ✅<br>• available as managed service from BD | ✅ | ❓ | ❓ | ❓ | ❓ | ✅ | ✅ |
| | | | | | | | | |
| **Decision** | Azure ML Jobs & Pipelines or Databricks Jobs & Workflows | | | | | | | |
| Justification | • Argo Workflows, Flyte, Kubeflow Pipelines and Prefect drop out because their Kubernetes dependency (for a production setup) and the thus too high maintenance effort<br>• additionally, for Flyte and Prefect, there are no information regarding a already done cloud onboarding for the managed cloud services<br>• Kedro is more about authoring pipelines and not an orchestrator itself, but rather integrates with other solutions (Airflow, Kubeflow, ...). It might be interesting to investigate this at later point regarding use on top of an existing workflow orchestration tool, but is omitted here.<br>• Apache Airflow would need no Kubernetes but the deployment and maintenance as well as the usage still seems complex. Still, this could get obtained via BD without the maintainability effort<br>• Azure ML and Databricks provide both an easy and scalable solution integrated directly with Azure but the computing resources will have no direct access to resources on-premise | | | | | | | |
| Decided by | | | | | | | | |
| Date of decision | <[dd.mm](http://dd.mm).yyyy> | | | | | | | |
| Comments / Conditions to be met | <bullet point list, task tracking issues> | | | | | | | |
| Related Decisions | <link to related decision> | | | | | | | |

## References

1. https://www.projectpro.io/article/best-mlops-tools-/574
2. https://neptune.ai/blog/best-open-source-mlops-tools
3. https://www.xenonstack.com/blog/mlops-tools
4. https://www.datacamp.com/blog/top-mlops-tools
5. https://neptune.ai/blog/mlops-tools-platforms-landscape
