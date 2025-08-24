
| | |
|-------|---------|
| **Name** | 35 Component - Experiment Tracking & Metadata Store |
| **Status** | DECIDED |
| **Context / Problem / Issue Description** | An essential part of a machine learning project is experiment tracking and metadata storage to document experiments, track performance, and manage metadata. Here, we compare tools for experiment tracking and metadata storage to enhance reproducibility and organization in ML workflows. |


| **Options considered** | **Option A** | **Option B** | **Option C** | **Option D** | **Option E** | **Option F** | **Option G** |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **Name & Link** | [Aim](https://aimstack.io/) | [CML](https://cml.dev/) | [Guild AI](https://github.com/guildai/guildai) | [TensorBoard](https://www.tensorflow.org/tensorboard) | [MLflow](https://mlflow.org/) Tracking | [Azure ML](https://azure.microsoft.com/en-us/products/machine-learning) Experiments | [Databricks](https://www.databricks.com/) Experiments |
| **Description** | An easy-to-use & supercharged open-source AI metadata tracker | Tool for implementing continuous integration & delivery (CI/CD) in machine learning projects | Toolkit for experiment tracking, optimization, and reproducibility | Provides the visualization and tooling needed for machine learning experimentation | The MLflow Tracking is an API and UI for logging parameters, code versions, metrics, and output files when running your machine learning code and for later visualizing the results | Experiment Tracking feature included into the Job component inside of Azure ML, supports Mflow format | Provides Experiment tracking via integrated MLflow |
| **License & Cost** | • Apache 2.0<br>• free | • MIT license<br>• free | • Apache 2.0<br>• free | • Apache 2.0<br>• free | • Apache 2.0<br>• free | • enterprise<br>• pay per use | • open core<br>• pay per use |
| **Documentation** | https://aimstack.readthedocs.io/en/latest/ | https://cml.dev/doc | https://github.com/guildai/guildai (no website with documentation anymore, domain for sale) | https://www.tensorflow.org/tensorboard/get_started | https://mlflow.org/docs/latest/tracking.html | https://learn.microsoft.com/en-us/azure/machine-learning/data-science-virtual-machine/how-to-track-experiments?view=azureml-api-2 | https://docs.databricks.com/en/mlflow/experiments.html |
| **Infrastructure / How to run it** | • can be run locally via PIP install<br>• can run on-premise or in cloud infrastructure via Docker or on Kubernetes (no Chart, only deployment files)<br>• needs storage volume | • runs in CI/CD pipeline (GitHub, GitLab)<br>• supports self-hosted runners, either on-premise or in the cloud (Azure, AWS, GCP)<br>• supports Kubernetes | • can be run locally via PIP install or via Docker<br>• no docs about on-premise or cloud deployment | • typically used with TensorFlow, but can be used with other frameworks<br>• used directly in notebooks like Jupyter | • can run on local machines, on-premise servers or cloud infrastructure | • managed service as part of Azure ML | • managed service as part of Databricks |
| **Academia** |  |  |  |  |  |  |  |
| **Advantages** | • efficient and visually pleasing user interface ¹<br>• tailored to manage vast volumes of tracked metadata sequences ¹<br>• all pertinent information is centralized ¹ | • flexible and provides a wide range of functionality; from sending reports and publishing data, to distributing cloud resources for a project ¹ | • archive runs to remote systems such as S3 ¹<br>• Hyperparameter Tuning with AutoML ¹ | • large library of pre-built tracking tools and easy integration ² | • intuitive Python API to log the parameters and metrics of each experiment, as well as the artifacts produced by the ML pipeline ³<br>• logged information can be visualized and compared using a web UI ³<br>• provides an advanced metadata store in combination with the model registry ⁴ |  |  |
| **Disadvantages** |  |  |  | • may not scale well with large experiments ² |  |  |  |
| **Requirements** |  |  |  |  |  |  |  |
| Compatibility with Azure | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Compatibility with GitHub | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| No own Kubernetes needed | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| | | | | | | | |
| Supports all kinds of ML | ❓ | ❓ | ❓ | ❌ focus on Tensorflow, support for some other libraries | ✅ | ✅ | ✅ |
| Supports on-premise | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| | | | | | | | |
| **User Experience** | • user-friendly, interactive UI | • integrated well with Git workflows | • CLI based, may have a steeper learning curve | • user-friendly<br>• seamless integration with TensorFlow | • user-friendly, intuitive UI<br>• well-documented | • user-friendly, interactive UI<br>• good integration with Azure ML | • user-friendly, intuitive UI<br>• well-documented<br>• good integration with Databricks |
| **Maintainability** | • depends on deployment setup | • requires Git and CI setup<br>• low ongoing maintenance | • simple to maintain | • simple to maintain<br>• requires TensorFlow setup | • easy to maintain but depending on deployment setup<br>• large community support | • managed service, low maintenance effort | • managed service, low maintenance effort |
| **Integration with CI/CD concept** | • integrates with CI/CD | • excellent integration with CI/CD | • integrates with CI/CD | • basic integration through TensorFlow | • integration with CI/CD via APIs and plugins | • integrates with CI/CD | • integrates with CI/CD |
| **Reliability & Stability** | • reliable, growing community support | • reliable | • reliable, but smaller community support | • reliable, mature | • highly reliable and mature | • reliable, enterprise | • reliable, enterprise |
| **Modularity & Reusability** | • modular, supports multiple ML frameworks | • modular, fits well into CI pipelines | • modular, supports multiple ML frameworks | • primarily focused on TensorFlow | • modular, supports multiple ML frameworks | • integrated into Azure ML platform but still modular as supporting the MLflow format<br>• cross-usage of Experiment Tracking component form Azure Databricks possible | • integrated into Databricks but still modular as basically just an integrated MLflow |
| **Performance & Scalability** | • good performance, scalable | • good performance, depends on CI infrastructure | • good performance, lightweight | • good performance, scales within TensorFlow | • good performance, scales well with distributed setups | • good performance, scales well with distributed setups | • good performance, scales well with distributed setups |


| **Decision** | **Option G: Databricks** (which is basically a managed **Option E: MLflow**) |
|-------|-------|
| **Justification** | • TensorBoard is dropped as it is a solution mainly tailored towards use with TensorFlow. <br>• MLflow is in widespread use but as both platforms Azure ML and Databricks provide the same Experiments functionality on top of many more, it makes no sense to use a dedicated MLflow for this component. In case there exists an on-premise Usecase for which Azure ML and Databricks cannot be used, an on-premise MLflow (possible to get as managed service from BD) would be a good solution and would work very similar as the experiment tracking provided by Azure ML or Databricks. <br>• Databricks provides an integrated MLflow and Azure ML an MLflow compatible Experiments feature. As one of these platforms will be used and both provide compatibility to the widespread MLflow format it makes sense to use this integrated functionality. <br>• Aim and GuildAI provide two alternatives to MLflow, mainly for local tracking of experiments but just provide no necesary additional features compared with the experiment tracking at Azure ML and Databricks. <br>• CML focuses on presenting results inside of CI pipelines. This does not seem to directly cover the intended functionality of this component, but could possibly be kept in mind for additional functionalities (adding reports to CI runs, ...) <br> • following the decision in favor of Databricks as platform, the decision is here also made for the corresponding Databricks component |
| **Decided by** |  |
| **Date of decision** | 31.07.24 |
| **Comments / Conditions to be met** |  |
| **Related Decisions** |  |

---

1. [Neptune.ai Open Source MLOps Tools](https://neptune.ai/blog/best-open-source-mlops-tools)
2. [IEEE MLOps Paper](https://ieeexplore.ieee.org/document/9792270)
3. [IEEE Data Quality in MLOps](https://ieeexplore.ieee.org/document/10172734)
4. [IEEE MLOps Framework](https://ieeexplore.ieee.org/document/10081336)
