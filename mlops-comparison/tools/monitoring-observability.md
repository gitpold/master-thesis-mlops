# 39 Component - Monitoring & Observability

| Name | 39 Component - Monitoring & Observability | | | | | | |
|------|------|------|------|------|------|------|------|
| Status | DRAFT | | | | | | |
| **Context / Problem / Issue Description** | A crucial aspect of a machine learning project is monitoring and observability to ensure models perform reliably in production. Effective tools in this area enable tracking model performance, detecting model drift, and maintaining overall system health. Here we compare several monitoring and observability tools to enhance model reliability and performance over time. | | | | | | |
| **Options considered** | Option A | Option B | Option C | Option D | Option E | Option F | Option G |
| Name & Link | [Arize AI](https://arize.com/) | [Evidently AI](https://www.evidentlyai.com/) | [Prometheus](https://prometheus.io/) + [Grafana](https://grafana.com/) | [Fiddler](https://www.fiddler.ai/) | [Helicone](https://www.helicone.ai/) | [LangFuse](https://langfuse.com/) | [Azure ML ](https://azure.microsoft.com/en-us/products/machine-learning)Monitoring |
| Description | AI Observability & LLM Evaluation Platform | ML observability platform that helps evaluate, test, and monitor data and ML-powered systems. | Systems monitoring and alerting toolkit + logging, metrics, traces, and profiling platform | Enterprise AI observability | LLM-Observability platform for logging, monitoring, and debugging | Open Source<br/>LLM Engineering Platform | Model Monitoring feature integrated into Azure ML platform |
| License & Cost | • proprietary<br/>• paid (different pricing tiers) | • Apache 2.0<br/>• free<br/>• managed cloud version with different pricing tiers | • Prometheus Apache 2.0<br/>• Grafana AGPL-3.0<br/>• free<br/>• managed cloud version with different pricing tiers for Grafana + Proemtheus | • proprietary<br/>• paid (different pricing tiers) | • Apache 2.0<br/>• free<br/>• managed cloud version with different pricing tiers | • MIT license<br/>• managed cloud version with different pricing tiers<br/>• self-hosting free | • enterprise<br/>• pay per use |
| Documentation | https://arize.com/docs/ | https://docs.evidentlyai.com/ | https://prometheus.io/docs/introduction/overview/<br/>https://grafana.com/docs/ | https://docs.fiddler.ai/docs/welcome | https://docs.helicone.ai/getting-started/quick-start | https://langfuse.com/docs | https://learn.microsoft.com/en-us/azure/machine-learning/monitor-azure-machine-learning?view=azureml-api-2 |
| Infrastructure / How to run it | • managed cloud version<br/>• for enterprise version self-hosting on Kubernetes on-premise or with cloud provider (GCP, AWS, Azure) possible | • managed cloud version<br/>• self-hosting locally on developer machine possible<br/>• no documentation on deployment via Docker/Helm to servers on-premise or on cloud provider | • self-hosting on server or Kubernetes possible | • manged cloud version<br/>• self-hosting on-premise or with cloud provider via Helm Chart on Kubernetes possible (very complex Helm Chart, many dependencies) | • managed cloud version<br/>• self-hosting on-premise or on cloud provider possible via Docker or a Helm Chart (in Beta) on Kubernetes | • managed cloud version<br/>• self-hosted version can be deployed via Docker, via Helm Chart to Kubernetes and different cloud providers (GCP, Azure, Heroku) | • managed service as part of Azure ML |
| **Academia** | | | | | | | |
| Advantages | • simple integration, pre-launch validation and automatic monitoring ¹<br/>• provides various tools for monitoring model performance, detecting drift, and identifying issues with data quality ² | • integration with Pandas DataFrames ¹<br/>• generates interactive reports form Pandas DataFrame ²<br/>• offers services for tabular data, embeddings, and text-based models and data ³<br/>• offers services towards LLMs ³<br/>• checks data and model quality ⁴ | | • easy-to-use, clear UI ⁴<br/>• provides performance monitoring, data integrity, tracking outliers, service metrics, and alerts ⁴ ⁵ foo<br/>• provides tools for explaining model predictions ² | | | |
| Disadvantages | • might be expensive ¹ | • only works with tabular and text data | | | | | |
| **Requirements** | | | | | | | |
| Compatibility with Azure | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Compatibility with GitHub | n.a. | n.a. | n.a. | n.a. | n.a. | n.a. | n.a. |
| No own Kubernetes needed | ❌ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ |
| | | | | | | | |
| Allowed at Bosch | ❓<br/>• no cloud onboarding information | ✅ | ✅ | ❓<br/>• no cloud onboarding information | ✅ | ✅ | ✅ |
| Supports all kinds of ML | ✅ | ❌ only text data, no images | (✅) needs custom efforts | ✅ | ❌ focus on LLMs | ❌ focus on LLMs / RAGs | ❓ |
| Supports on-premise | (✅) | ✅ | ✅ | (✅) | ✅ | ✅ | ❌ |
| | | | | | | | |
| User Experience | • intuitive, user-friendly UI | • user-friendly, clear dashboards | • requires configuration<br/>• steeper learning curve | • intuitive, user-friendly UI | • intuitive, user-friendly UI | • intuitive, user-friendly UI | • well integrated into Azure ML platform |
| Maintainability | • low maintenance (managed service) | • requires some local setup but no ongoing maintenance effort | • requires ongoing maintenance and updates | • low maintenance (managed service) | • medium to high effort for self-hosted deployment and maintenance needed | • some effort for self-hosted deployment and maintenance needed | • managed service, low maintenance effort |
| Integration with CI/CD concept | n.a. | n.a. | n.a. | n.a. | n.a. | n.a. | n.a. |
| Reliability & Stability | • reliable, mature | • reliable, growing community support | • open source but still highly reliable and mature | • reliable, strong community support | • reliable, but newer tool | • reliable, but newer tool | • reliable, enterprise |
| Modularity & Reusability | • modular, integrates with various ML tools | • modular, integrates with various ML tools | • highly modular, integrates with various tools | • modular, integrates with various ML tools | • limited modularity, focus on specific use cases (LLMs) | • limited modularity, focus on specific use cases (LLMs) | |
| Performance & Scalability | • good performance, scalable | • good performance, scalable | • good performance, scalable | • good performance, scalable | • good performance, scalable | • good performance, scalable | • good performance, scalable |
| | | | | | | | |
| Tool already existing at Bosch | ❓ | ✅ | ✅ | ❓ | ❌ | ✅ | **✅** |
| | | | | | | | |
| **Decision** | • in case of Azure ML as platform: Azure ML Monitoring + possibly LangFuse or Helicone for LLM/RAG related monitoring<br/>• in case of Databricks: possibly Evidently for classical ML model monitoring + possibly LangFuse or Helicone for LLM/RAG related monitoring | | | | | | |
| Justification | • Prometheus + Grafana could make sense to use if it is already in place, but just for the model monitoring this solution leads to too high setup and maintenance efforts<br/>• both Arize AI and Fiddler are dropped from the closer selection as they would need a cloud onboarding for the use as a managed cloud service and depend on a Kubernetes cluster for on-premise deployment (and still need a paid license)<br/>• Azure ML Monitoring seems to provide a well-integrated Model Monitoring solution, if using Azure ML this should provide the necessary features for monitoring of classical models (coverage of LLM/RAG monitoring unsure)<br/>• Evidently provides only support for text data but is an open-source and low effort solution which could be used to monitor performance of classical ML models in case the used platform does not provide enough features<br/>• Helicone and LangFuse focus only on monitoring of LLM/RAG solutions but could possibly extend the monitoring features of a platform in that regard | | | | | | |
| Decided by | | | | | | | |
| Date of decision | <[dd.mm](http://dd.mm).yyyy> | | | | | | |
| Comments / Conditions to be met | <bullet point list, task tracking issues> | | | | | | |
| Related Decisions | <link to related decision> | | | | | | |

## References

1. https://ieeexplore.ieee.org/document/9792270
2. https://neptune.ai/blog/mlops-tools-platforms-landscape
3. https://neptune.ai/blog/best-open-source-mlops-tools
4. https://www.datacamp.com/blog/top-mlops-tools
5. https://www.xenonstack.com/blog/mlops-tools
