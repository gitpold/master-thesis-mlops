
| | |
|-------|---------|
| **Name** | 30 Component - Data Labeling |
| **Status** | OPEN |
| **Context / Problem / Issue Description** | A big part of a machine learning project is getting enough data to train a model. Often this data has to be labeled manually at the beginning. This can be done completely manually or with tool support, including (partial) automation of the labeling process. Here different tools that support the labeling process are compared. |


| **Options considered** | **Option A** | **Option B** | **Option C** | **Option D** | **Option E** |
| --- | --- | --- | --- | --- | --- |
| **Name & Link** | [Labelbox](https://labelbox.com/) | [Scale](https://scale.com/) | [Snorkel Flow](https://snorkel.ai/) | [Doccano](https://doccano.github.io/doccano/) | [Azure ML](https://azure.microsoft.com/en-us/products/machine-learning) Data Labeling |
| **Description** | Data labeling platform offering annotation tools for text, image, and video labeling | Data labeling platform that focuses on high-quality annotations for AI training data | Data-centric platform for creating and managing training data through programmatic labeling | Text annotation tool supporting text classification, sequence labeling, and sequence-to-sequence tasks | Data Labeling component for image, text, and audio data providing management of labelers |
| **License & Cost** | • proprietary<br>• paid (different pricing tiers) | • proprietary<br>• paid | • proprietary<br>• paid | • MIT license<br>• free | • enterprise<br>• included with Azure ML |
| **Documentation** | https://docs.labelbox.com/ | https://scale.com/docs | https://docs.snorkel.ai/ | https://doccano.github.io/doccano/ | https://learn.microsoft.com/en-us/azure/machine-learning/how-to-create-image-labeling-projects?view=azureml-api-2 |
| **Infrastructure / How to run it** | • managed cloud-based service<br>• for enterprise clients on-premise deployment option | • manged service in the cloud | • exists as managed service<br>• can be deployed to cloud provider (AWS, GCP, Azure) or on private cloud with Kubernetes | • can be run locally via PIP or Docker<br>• can be run on cloud infrastructure<br>• for cloud storage supports AWS S3 and Google Cloud Storage | • managed service as part of Azure ML |
| **Academia** |  |  |  |  |  |
| **Advantages** | • collaborative annotation, quality control, and automation capabilities ¹ | • combines human annotators and machine learning algorithms to deliver efficient and reliable annotations ¹<br>• includes object detection, semantic segmentation, and natural language processing¹ | • includes flexible label function creation, auto-labeling, active learning ¹ |  |  |
| **Disadvantages** |  |  |  |  |  |
| **Requirements** |  |  |  |  |  |
| Compatibility with Azure | ✅ | ✅ | ✅ | ✅ | ✅ |
| Compatibility with GitHub | n.a. | n.a. | n.a. | n.a. | n.a |
| No own Kubernetes needed | ✅ | ✅ | (✅) | ✅ | ✅ |
| | | | | | |
| Supports all kinds of ML | ✅ | ✅ | ✅ | ❌ (only for text data) | ✅ |
| Supports on-premise | (✅) | ❌ | (✅) | ✅ | ❌ |
| | | | | | |
| **User Experience** | • intuitive UI<br>• many different data types supported | • intuitive UI<br>• many different data types supported | • no documentation found (only of open source Python library Snorkel) | • provides simple UI | • UI integrated into Azure ML |
| **Maintainability** | • depends on setup<br>• for managed service low maintenance effort | • low maintenance effort (managed service) | • depends on setup<br>• for managed service low maintenance effort | • depends on setup<br>• low effort for local use<br>• higher effort for deployed component | • low maintenance effort (managed service) |
| **Integration with CI/CD concept** | n.a. | n.a. | n.a. | n.a. | n.a. |
| **Reliability & Stability** | • very reliable (managed service) | • very reliable (managed service) | • very reliable (managed service) | • reliable, big community | • very reliable (managed service) |
| **Modularity & Reusability** | • component could be reused for nearly every type of data<br>• modular in the sense that data can get extracted for further use in other tools | • component could be reused for nearly every type of data<br>• modular in the sense that data can get extracted for further use in other tools | • unclear | • provides import/export functionality allowing to use this as one module of a bigger process | • component integrated with Azure ML but result not locked in |
| **Performance & Scalability** | • highly scalable with any workforce, internal or external | • highly scalable with labeling workforce<br>• focus on using AI for labeling which further scales/improves the annotation process | • scales via focus on programmatic labeling | • supports multiple users but no support for labeling workforce | • highly scalable with the option to use external workforce / labeling companies |


| **Decision** | • Component has currently only a low priority and will not get considered in the first MLOps pipeline to set up <br>• In the closer selection would be Labelbox and Doccano (best decision depends on the use case) |
|-------|-------|
| **Justification** | • Labelbox is a paid service but supports many different data types, has as a managed service no high maintenance effort and seems to have already passed an onboarding<br>• Scale and Snorkel Flow would need to get onboarded first<br>• Doccano is only supporting text data, but is free and open-source<br>• Azure ML Data Labeling comes as part of the Azure ML platform, provides many features and needs no additional maintenance effort. However, as the decision for the platform was made in favor of Databricks, Azure ML just for the Data Labeling might be feasible but seems like a high effort |
| **Decided by** |  |
| **Date of decision** | 31.07.24 |
| **Comments / Conditions to be met** | |
| **Related Decisions** | |

---

1. [Neptune.ai MLOps Tools Platforms Landscape](https://neptune.ai/blog/mlops-tools-platforms-landscape)
