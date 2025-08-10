# 38 Component - Model Deployment & Serving

| Name | 38 Component - Model Deployment & Serving | | | | | | |
|------|------|------|------|------|------|------|------|
| Status | DRAFT | | | | | | |
| **Context / Problem / Issue Description** | A vital part of a machine learning project is model deployment and serving, ensuring models are effectively integrated into production. Tools in this area should support batch and event processing, as well as different rollout patterns such as canary and blue-green deployments. Here we compare various model deployment and serving tools to optimize the integration and performance of ML models in production. | | | | | | |
| **Options considered** | Option A | Option B | Option C | Option D | Option E | Option F | Option G |
| Name & Link | [Seldon Core](https://www.seldon.io/) | [KServe](https://kserve.github.io/website/latest/) ([Kubeflow](https://www.kubeflow.org/)) | [BentoML](https://www.bentoml.com/) | [LangServe](https://python.langchain.com/v0.2/docs/langserve/) | [Ray Serve](https://docs.ray.io/en/latest/serve/index.html) | [Azure ML ](https://azure.microsoft.com/en-us/products/machine-learning)Endpoints | [Databricks ](https://www.databricks.com/)Serving |
| Description | An MLOps framework to package, deploy, monitor and manage machine learning models | Highly scalable and standards based<br/>Model Inference Platform on Kubernetes | model serving library for building performant and scalable AI applications with Python | Helps developers deploy LangChain runnables and chains as a REST API | Ray Serve is a scalable model serving library for building online inference APIs | Model Serving feature integrated into Azure ML platform | Model Serving feature integrated into Databricks platform |
| License & Cost | • Business Source License (Apache 2.0 after 4 years)<br/>• free only for non-production<br/>• Seldon ML Server is open source & free | • Apache 2.0<br/>• free | • Apache 2.0<br/>• free | • open source<br/>• free | • Apache 2.0<br/>• free | • enterprise<br/>• pay per use | • open core<br/>• pay per use |
| Documentation | https://docs.seldon.io/ | https://kserve.github.io/website/latest/ | https://docs.bentoml.com/en/latest/ | https://python.langchain.com/v0.2/docs/langserve/ | https://docs.ray.io/en/latest/serve/index.html | https://learn.microsoft.com/en-us/azure/machine-learning/concept-endpoints?view=azureml-api-2 | https://docs.databricks.com/en/machine-learning/model-serving/index.html |
| Infrastructure / How to run it | • installed to Kubernetes via Helm Chart | • is deployed to Kubernetes (via install script or Helm Chart) | • Python package, can be installed via PIP on Linux, Windows or macOS<br/>• can deploy to BentoCloud or build into Docker container | • Python package, can be installed via PIP<br/>• builds into Docker container including FastAPI<br/>• can be deployed to container service on AWS, Azure, GCP<br/>• hosted version of LangServe announced | • can be installed on single server or on Kubernetes | • managed service as part of Azure ML | • managed service as part of Databricks |
| **Academia** | | | | | | | |
| Advantages | • custom offline models ¹<br/>• real-time predictions that expose APIs to external clients ¹<br/>• Web UI and CLI, OpenAPI ²<br/>• Prometheus and Grafana integration ² ³<br/>• Easy way to containerize ML models using our pre-packaged inference servers, custom servers, or language wrappers ³<br/>• advanced solutions for measuring model performance, detecting outliers, and conducting A/B testing out-of-the-box ⁴ | • offers monitoring and status control ¹ | • auto-generation of API servers, REST APIs (Swagger/OpenAPI), gRPC, and long-running inference jobs ⁵ ² ⁶<br/>• offers auto-generation of Docker container images ⁵<br/>• support many runtimes like Kubernetes clusters, Azure Functions, AWS Lambda ⁶<br/>• works with all kinds of machine learning frameworks, such as Keras, ONNX, LightGBM, Pytorch, and Scikit-learn ⁷ ⁴<br/>• CLI and Web UI ⁷ ² | | • Ray framework provides also other components ⁷ | | |
| Disadvantages | • set up can be a bit complex ⁸ | • difficult to set up and configure manually ¹ | | | | | |
| **Requirements** | | | | | | | |
| Compatibility with Azure | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Compatibility with GitHub | n.a. | n.a. | n.a. | n.a. | n.a. | n.a. | n.a. |
| No own Kubernetes needed | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ |
| | | | | | | | |
| Allowed at Bosch | ❓ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Supports all kinds of ML | ❓ | ❓ | ❓ | ❌ for LLMs | ❓ | ✅ | ✅ |
| Supports on-premise | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| | | | | | | | |
| User Experience | • comprehensive but complex setup<br/>• good documentation | • Kubernetes expertise required/helpful | • straightforward CLI and API | • simple API | • integrates well with Ray ecosystem | • good integration with Azure ML platform<br/>• can be used via UI, SDK, or ARM Template | • good integration with Databricks platform<br/>• can be used via UI or TF |
| Maintainability | • Kubernetes management needed | • Kubernetes management needed | • easy<br/>• no hosted deployment that needs to get maintained | • easy<br/>• no hosted deployment that needs to get maintained | • integrated with Ray, potentially effort for other needed components? | • managed service, low maintenance effort | • managed service, low maintenance effort |
| Integration with CI/CD concept | • well integrated with Kubernetes based CI/CD | • well integrated with Kubernetes based CI/CD | • good CI/CD integration | • CI/CD integration possible | • CI/CD integration possible<br/>• integration with Ray | • CI/CD integration possible | • CI/CD integration possible |
| Reliability & Stability | • reliable, mature | • reliable, Kubernetes native | • reliable | • reliable, but newer and less mature | • reliable, leverages Rays stability | • reliable, enterprise | • reliable, enterprise |
| Modularity & Reusability | • highly modular, supports various ML frameworks | • highly modular, supports various ML frameworks | • modular, supports various ML frameworks | • modular<br/>• focused on language models | • modular | • not as modular as integrated with Azure ML platform but supports multiple deployment targets | • not as modular as integrated with Databricks platform, but for example via MLflow and Azure ML supports deployment to multiple targets |
| Performance & Scalability | • high performance, scalable on Kubernetes | • high performance, scalable on Kubernetes | • good performance, can scale with Kubernetes or other environments | • designed for scalable language model serving | • high performance, scalable with Ray clusters | • high performance, scalable | • high performance, scalable |
| | | | | | | | |
| Tool already existing at Bosch | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ |
| | | | | | | | |
| **Decision** | Azure ML or Databricks, possibly LangServe for RAG apps | | | | | | |
| Justification | • Azure ML and Databricks provide both a complete model serving feature which makes sense to rely on when using the platform<br/>• KServe is dropped from the selection because of the Kubernetes dependency<br/>• Seldon Core is dropped from the selection because of the Kubernetes dependency and the additional uncertainty of the required license<br/>• Ray Serve would support on-premise use case without the need for a Kubernetes cluster, additionally it is provided by BD as a service. But as long as the model can be allowed to be hosted in the cloud, using the integrated functionality of Azure ML or Databricks will be easier<br/>• BentoML does not directly provide a Model Serving platform but is a tool for packaging models into Docker containers. As both Azure ML and Databricks should support the serving of most model types directly this feature will not be needed. It would make sense to use this if there is no dedicated model serving platform but only the possibility to run Docker containers<br/>• LangFuse does not directly provide a Model Serving platform but is a tool for packaging LangChain runnables into a Docker container with a REST API. This could be an additional feature helpful for developing LLM/RAG applications which is not directly provided by the serving components of Azure ML or Databricks | | | | | | |
| Decided by | | | | | | | |
| Date of decision | <[dd.mm](http://dd.mm).yyyy> | | | | | | |
| Comments / Conditions to be met | <bullet point list, task tracking issues> | | | | | | |
| Related Decisions | <link to related decision> | | | | | | |

## References

1. https://ieeexplore.ieee.org/document/9792270
2. https://www.xenonstack.com/blog/mlops-tools
3. https://neptune.ai/blog/mlops-tools-platforms-landscape
4. https://neptune.ai/blog/best-open-source-mlops-tools
5. https://dzone.com/articles/mlops-architectural-models-advanced-guide
6. https://www.projectpro.io/article/best-mlops-tools-/574
7. https://www.datacamp.com/blog/top-mlops-tools
8. https://ieeexplore.ieee.org/document/9792270
