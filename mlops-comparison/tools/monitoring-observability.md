
| | |
|-------|---------|
| **Name** | 39 Component - Monitoring & Observability |
| **Status** | DECIDED |
| **Context / Problem / Issue Description** | A crucial aspect of a machine learning project is monitoring and observability to ensure models perform reliably in production. Effective tools in this area enable tracking model performance, detecting model drift, and maintaining overall system health. Here we compare several monitoring and observability tools to enhance model reliability and performance over time. |


| **Options considered** | **Option A** | **Option B** | **Option C** | **Option D** | **Option E** | **Option F** | **Option G** |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **Name & Link** | [Arize AI](https://arize.com/) | [Evidently AI](https://www.evidentlyai.com/) | [Prometheus](https://prometheus.io/) + [Grafana](https://grafana.com/) | [Fiddler](https://www.fiddler.ai/) | [Helicone](https://www.helicone.ai/) | [LangFuse](https://langfuse.com/) | [Azure ML](https://azure.microsoft.com/en-us/products/machine-learning) Monitoring |
| **Description** | AI Observability & LLM Evaluation Platform | ML observability platform that helps evaluate, test, and monitor data and ML-powered systems. | Systems monitoring and alerting toolkit + logging, metrics, traces, and profiling platform | Enterprise AI observability | LLM-Observability platform for logging, monitoring, and debugging | Open Source<br/>LLM Engineering Platform | Model Monitoring feature integrated into Azure ML platform |
| **License & Cost** | • proprietary<br/>• paid (different pricing tiers) | • Apache 2.0<br/>• free<br/>• managed cloud version with different pricing tiers | • Prometheus Apache 2.0<br/>• Grafana AGPL-3.0<br/>• free<br/>• managed cloud version with different pricing tiers for Grafana + Proemtheus | • proprietary<br/>• paid (different pricing tiers) | • Apache 2.0<br/>• free<br/>• managed cloud version with different pricing tiers | • MIT license<br/>• managed cloud version with different pricing tiers<br/>• self-hosting free | • enterprise<br/>• pay per use |
| **Documentation** | https://arize.com/docs/ | https://docs.evidentlyai.com/ | https://prometheus.io/docs/introduction/overview/<br/>https://grafana.com/docs/ | https://docs.fiddler.ai/docs/welcome | https://docs.helicone.ai/getting-started/quick-start | https://langfuse.com/docs | https://learn.microsoft.com/en-us/azure/machine-learning/monitor-azure-machine-learning?view=azureml-api-2 |
| **Infrastructure / How to run it** | • managed cloud version<br/>• for enterprise version self-hosting on Kubernetes on-premise or with cloud provider (GCP, AWS, Azure) possible | • managed cloud version<br/>• self-hosting locally on developer machine possible<br/>• no documentation on deployment via Docker/Helm to servers on-premise or on cloud provider | • self-hosting on server or Kubernetes possible | • manged cloud version<br/>• self-hosting on-premise or with cloud provider via Helm Chart on Kubernetes possible (very complex Helm Chart, many dependencies) | • managed cloud version<br/>• self-hosting on-premise or on cloud provider possible via Docker or a Helm Chart on Kubernetes | • managed cloud version<br/>• self-hosted version can be deployed via Docker, via Helm Chart to Kubernetes and different cloud providers (GCP, Azure, Heroku) | • managed service as part of Azure ML |
| **Academia** |  |  |  |  |  |  |  |
| **Advantages** | • simple integration, pre-launch validation and automatic monitoring ¹<br/>• provides various tools for monitoring model performance, detecting drift, and identifying issues with data quality ² | • integration with Pandas DataFrames ¹<br/>• generates interactive reports form Pandas DataFrame ²<br/>• offers services for tabular data, embeddings, and text-based models and data ³<br/>• offers services towards LLMs ³<br/>• checks data and model quality ⁴ |  | • easy-to-use, clear UI ⁴<br/>• provides performance monitoring, data integrity, tracking outliers, service metrics, and alerts ⁴ ⁵ <br/>• provides tools for explaining model predictions ² |  |  |  |
| **Disadvantages** | • might be expensive ¹ | • only works with tabular and text data |  |  |  |  |  |
| **Requirements** |  |  |  |  |  |  |  |
| Compatibility with Azure | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Compatibility with GitHub | n.a. | n.a. | n.a. | n.a. | n.a. | n.a. | n.a. |
| No own Kubernetes needed | ❌ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ |
| | | | | | | | |
| Supports all kinds of ML | ✅ | ❌ only text data, no images | (✅) needs custom efforts | ✅ | ❌ focus on LLMs | ❌ focus on LLMs / RAGs | ❓ |
| Supports on-premise | (✅) | ✅ | ✅ | (✅) | ✅ | ✅ | ❌ |
| | | | | | | | |
| **User Experience** | • intuitive, user-friendly UI | • user-friendly, clear dashboards | • requires configuration<br/>• steeper learning curve | • intuitive, user-friendly UI | • intuitive, user-friendly UI | • intuitive, user-friendly UI | • well integrated into Azure ML platform |
| **Maintainability** | • low maintenance (managed service) | • requires some local setup but no ongoing maintenance effort | • requires ongoing maintenance and updates | • low maintenance (managed service) | • medium to high effort for self-hosted deployment and maintenance needed | • some effort for self-hosted deployment and maintenance needed | • managed service, low maintenance effort |
| **Integration with CI/CD concept** | n.a. | n.a. | n.a. | n.a. | n.a. | n.a. | n.a. |
| **Reliability & Stability** | • reliable, mature | • reliable, growing community support | • open source but still highly reliable and mature | • reliable, strong community support | • reliable, but newer tool | • reliable, but newer tool | • reliable, enterprise |
| **Modularity & Reusability** | • modular, integrates with various ML tools | • modular, integrates with various ML tools | • highly modular, integrates with various tools | • modular, integrates with various ML tools | • limited modularity, focus on specific use cases (LLMs) | • limited modularity, focus on specific use cases (LLMs) |  |
| **Performance & Scalability** | • good performance, scalable | • good performance, scalable | • good performance, scalable | • good performance, scalable | • good performance, scalable | • good performance, scalable | • good performance, scalable |


| **Decision** | **Option F: Langfuse** and **Databricks** integrated monitoring & observability capabilities |
|-------|-------|
| **Justification** | • Prometheus + Grafana could make sense to use if it is already in place, but just for the model monitoring this solution leads to too high setup and maintenance efforts. <br> • Both Arize AI and Fiddler are dropped from the closer selection as they would need a cloud onboarding for the use as a managed cloud service and depend on a Kubernetes cluster for on-premise deployment (and still need a paid license). <br> • Azure ML Monitoring seems to provide a well-integrated Model Monitoring solution, if using Azure ML this should provide the necessary features for monitoring of classical models (coverage of LLM/RAG monitoring unsure). However, as the platform decision has been made in favor of Databricks over Azure ML, the model monitoring feature of Azure ML will not get used <br> • Evidently provides only support for text data but is an open-source and low effort solution which could be used to monitor performance of classical ML models. While mainly used locally, it can get deployed together with a collector service to send data to it. Still, mainly because of it only supporting tabular and text data and no image data, this is rather not a general solutionbut could get employed depnding on the use case <br> • Helicone provides a whole observability platform for LLMs with many features (proxy requests for cost monitoring, rate limiting, caching, alerting, dashboards, LLM security, billing of fine-tuned models, LLM evaluations), at least currently the focus of this tool, however, is not on visualizing LLM evaluations. Because of the multiple dependencies of the deployment, this would have a medium to high effort for deploying the solution (cannot be deployed as a single container) <br> • Langfuse focuses on monitoring/tracing of LLM/RAG solutions with the possibility to display LLM evaluations. Deployment is simple as it can be deployed via a single container, or with a more advanced architecture in order to support higher loads. Deployment supports SSO setup. The team has already experience with Langfuse. <br> • Alternative decision of Arize Phoenix for LLM monitoring was discarded in favor of Option F: Langfuse after findings from implementation phase <br> • possible candidates Option B: Evidently AI and Deepchecks for classical ML monitoring were discarded in favor of integrated monitoring capabilities in Databricks (inference tables with calculation of metrics on the entries and visualization via dashboards in Databricks) after findings from implementation phase |
| **Decided by** |  |
| **Date of decision** | 24.08.24 |
| **Comments / Conditions to be met** | |
| **Related Decisions** | 36 Component - Model Testing & Validation |

---

1. [IEEE MLOps Paper](https://ieeexplore.ieee.org/document/9792270)
2. [Neptune.ai MLOps Tools Platforms Landscape](https://neptune.ai/blog/mlops-tools-platforms-landscape)
3. [Neptune.ai Open Source MLOps Tools](https://neptune.ai/blog/best-open-source-mlops-tools)
4. [DataCamp MLOps Tools](https://www.datacamp.com/blog/top-mlops-tools)
5. [Xenonstack MLOps Tools](https://www.xenonstack.com/blog/mlops-tools)
