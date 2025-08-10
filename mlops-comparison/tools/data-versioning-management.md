# 31 Component - Data Versioning & Management

Based on a rapid review of the white and grey literature on MLOps, the following tools were identified for the data versioning & management category:

- Delta Lake
- Dolt
- DVC
- LakeFS
- Pachyderm
- Qri
- Quilt

Since this list of tools is too extensive for a comprehensive evaluation of all entries, the following evaluation is limited to a subset of popular or promising tools.
In addition, some corresponding components of the platforms (if existing) or tools proposed by other means (e.g. by team members) are included in the comparison.

| Criteria | Option A | Option B | Option C | Option D | Option E | Option F |
|----------|----------|----------|----------|----------|----------|----------|
| **Name** | 31 Component - Data Versioning & Management |  |  |  |  |  |
| **Status** | DRAFT |  |  |  |  |  |
| **Context / Problem / Issue Description** | A key part of a machine learning project is managing and tracking data versions to ensure consistency and reproducibility. As this is very time-consuming to do manually, here, different tools for data versioning and management are compared. |  |  |  |  |  |
|  |  |  |  |  |  |  |
| **Options considered** | Option A | Option B | Option C | Option D | Option E | Option F |
| **Name & Link** | [DVC](https://dvc.org/) | [Pachyderm](https://www.pachyderm.com/) | [Delta Lake](https://delta.io/) | [LakeFS](https://lakefs.io/) | [Azure ML](https://azure.microsoft.com/en-us/products/machine-learning) Data Versioning | [Databricks](https://www.databricks.com/) Data Versioning |
| **Description** | Command line tool for data versioning and management | Data versioning and pipeline orchestration platform | Provides scalable and reliable data management on top of existing data lake infrastructure | Data versioning and management platform on data lakes | Custom data versioning integrated into Azure ML | Provides data versioning via integrated Delta Lake |
| **License & Cost** | • Apache 2.0<br>• free | • BSL (Non-standard license)<br>• free community version<br>• paid enterprise version | • Apache 2.0<br>• free | • Apache 2.0<br>• free | • enterprise<br>• pay per use | • open core<br>• pay per use |
| **Documentation** | https://dvc.org/doc | https://docs.pachyderm.com/ | https://docs.delta.io/latest/index.html | https://docs.lakefs.io/ | https://learn.microsoft.com/en-us/azure/machine-learning/how-to-version-track-datasets?view=azureml-api-1 | https://docs.databricks.com/en/delta/index.html |
| **Infrastructure / How to run it** | • Python package, can be installed via PIP<br>• runs locally integrated with existing Git repositories<br>• for remote data storage is a cloud storage (for example Azure Blob Storage) needed | • runs on Kubernetes (cloud or on-premise) | • integrated with Spark and runs on any Spark cluster<br>• uses existing cloud storage solutions as backend (for example Azure Data Lake Storage) | • can be deployed on cloud infrastructure or on-premise<br>• interfaces with object storage (for example Azure Blob Storage) | • managed service as part of Azure ML | • managed service as part of Databricks |
| **Academia** |  |  |  |  |  |  |
| **Advantages** | • lightweight and usable with all cloud platforms and storage types ¹<br>• Git-like interface allowing to track changes and mange branches ²<br>• data format agnostic & cloud agnostic ³<br>• simple to use ³<br>• provides data, model, metadata, and pipeline versioning ⁴ | • provides data lineage tracking and reproducibility features ⁵ ²<br>• syntax similar to Git ⁴<br>• data format agnostic & cloud agnostic ³<br>• simple to use ³<br>• easy support for big data ³ | • ACID transactions ¹<br>• provides metadata management ¹<br>• manages large-scale, structured and unstructured data with high performance ² | • allows to version and control changes to data lakes at scale ²<br>• Git-like version control interface ⁴<br>• data format agnostic ³<br>• easy support for big data ³<br>• supports pre-commit and merge hooks for CI/CD ⁴ |  |  |
| **Disadvantages** | • version control very coupled with pipeline management ¹ |  | • requires using a dedicated data format ¹ |  |  |  |
| **Requirements** |  |  |  |  |  |  |
| **Compatibility with Azure** | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| **Compatibility with GitHub** | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| **No own Kubernetes needed** | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ |
|  |  |  |  |  |  |  |
| **Allowed at Bosch** | ✅ | ❓<br>• no cloud onboarding info | ✅ | ✅ | ✅ | ✅ |
| **Supports all kinds of ML** | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| **Supports on-premise** | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
|  |  |  |  |  |  |  |
| **User Experience** | • simple CLI (git-like)<br>• UI via VS Code extension. or DVC Studio available | • intuitive UI<br>• CLI with git-like syntax | • not as simple to use | • not as simple to use | • simple solution<br>• good integration with Azure ML platform | • integrated with Databricks platform |
| **Maintainability** | • low maintenance, only running on machine and no deployed component | • higher maintenance, needs Kubernetes | • depending on setup | • some setup and maintenance effort | • managed service, low maintenance effort | • managed service, low maintenance effort |
| **Integration with CI/CD concept** | • integrates with CI/CD (CLI can be used in CI pipeline) | • integrates with CI/CD |  | • good integration with CI/CD (for example pre-commit and merge hooks) | • integrates with CI/CD |  |
| **Reliability & Stability** | • reliable, big community | • reliable, enterprise | • reliable | • reliable | • reliable, enterprise | • reliable, enterprise |
| **Modularity & Reusability** | • modular, can be used to together with other tools | • modular, integrates with other tools | • works in top of existing data lakes (such as S3, HDFS, ...)<br>• good integration with Databricks | • modular, integrates with many other tools | • not modular, integrated with Azure ML platform | • not modular, integrated with Databricks |
| **Performance & Scalability** | • performance issues with large amount of files | • scalable | • highly scalable with Spark | • scalable | • scalable | • highly scalable with Spark |
|  |  |  |  |  |  |  |
| **Tool already existing at Bosch** | ✅ | ❓ | ❓ | ✅ | ✅ | ✅ |
|  |  |  |  |  |  |  |
| **Decision** |  |  |  |  |  |  |
| **Justification** | • Delta Lake on its own is to complex with its dependency to Spark, but when using Databricks the integrated Delta Lake is the obvious choice<br>• Pachyderm is eliminated because of the dependency to Kubernetes and therefore higher maintenance effort as well as the missing onboarding information<br>• DVC?<br>• LakeFS?<br>• Azure ML Data Versioning seems like the obvious choice when using Azure ML but DVC or LakeFs could still provide additional features |  |  |  |  |  |
| **Decided by** |  |  |  |  |  |  |
| **Date of decision** | <dd.mm.yyyy> |  |  |  |  |  |
| **Comments / Conditions to be met** | <bullet point list, task tracking issues> |  |  |  |  |  |
| **Related Decisions** | <link to related decision> |  |  |  |  |  |

---

**References:**
1. [IEEE MLOps Paper](https://ieeexplore.ieee.org/document/9792270)
2. [Neptune.ai MLOps Tools Platforms Landscape](https://neptune.ai/blog/mlops-tools-platforms-landscape)
3. [Xenonstack MLOps Tools](https://www.xenonstack.com/blog/mlops-tools)
4. [DataCamp MLOps Tools](https://www.datacamp.com/blog/top-mlops-tools)
5. [Neptune.ai Open Source MLOps Tools](https://neptune.ai/blog/best-open-source-mlops-tools)
