# 32 Component - Feature Stores

Based on a rapid review of the white and grey literature on MLOps, the following tools were identified for the feature store category:

- Feast
- Featureform
- Hopswork
- Rasgo
- Tecton

Since this list of tools is too extensive for a comprehensive evaluation of all entries, the following evaluation is limited to a subset of popular or promising tools.
In addition, some corresponding components of the platforms (if existing) or tools proposed by other means (e.g. by team members) are included in the comparison.

| Criteria | Option A | Option B | Option C | Option D | Option E | Option F |
|----------|----------|----------|----------|----------|----------|----------|
| **Name** | 32 Component - Feature Stores |  |  |  |  |  |
| **Status** | DRAFT |  |  |  |  |  |
| **Context / Problem / Issue Description** | A key aspect of a machine learning project is managing features to ensure they are used consistently and efficiently across models. A feature store centralizes this process, enabling feature reuse, governance, and real-time serving. Here we compare several feature store management tools. |  |  |  |  |  |
|  |  |  |  |  |  |  |
| **Options considered** | Option A | Option B | Option C | Option D | Option E | Option F |
| **Name & Link** | [Feast](https://feast.dev/) | [Tecton](https://www.tecton.ai/) | [Hopswork](https://www.hopsworks.ai/the-python-centric-feature-store) | [Featureform](https://www.featureform.com/) |  |  |
| **Description** | feature store for machine learning enabling storage, retrieval, and management of features | feature store platform designed for building, managing, and serving machine learning features | data platform with an integrated feature store supporting feature engineering, storage, and serving | feature store designed to simplify the process of managing features for machine learning |  |  |
| **License & Cost** | • Apache License 2.0<br>• free | • proprietary<br>• paid service | • AGPL-3.0 license<br>• free open-source version (with less features)<br>• paid enterprise version | • MPL-2.0 license<br>• free open-source version<br>• paid enterprise version |  |  |
| **Documentation** | https://docs.feast.dev/ | https://docs.tecton.ai/ | https://docs.hopsworks.ai/latest/ | https://docs.featureform.com/introduction |  |  |
| **Infrastructure / How to run it** | • Python package, can be installed via PIP<br>• experimental UI might be able to get deployed (no docs)<br>• cloud storage for feature storage | • offered as a manged service<br>• needs cloud infrastructure (AWS, GCP, or Azure) for data storage and processing | • cloud or on-premise environment for deployment (enterprise version)<br>• can be installed alongside Kubernetes for orchestration<br>• serverless service (free version) | • locally or on cloud infrastructure<br>• supports cloud providers like AWS, Azure, and GCP<br>• can be run on Kubernetes |  |  |
| **Academia** |  |  |  |  |  |  |
| **Advantages** | • supports online and offline feature stores ¹ ²<br>• supports batch and real-time feature serving ³ | • provides components for feature engineering, feature storage, serving, and monitoring ³ | • to build, manage, and serve features while ensuring data lineage, governance, and collaboration ⁴ | • built-in role-based access control (enterprise version) ²<br>• can be used with any infrastructure ³ |  |  |
| **Disadvantages** |  |  |  |  |  |  |
| **Requirements** |  |  |  |  |  |  |
| **Compatibility with Azure** | ✅ | ❌ (no connection to Azure mentioned in docs) | ✅ | ✅ |  |  |
| **Compatibility with GitHub** | n.a. | n.a. | n.a. | n.a. |  |  |
| **No own Kubernetes needed** | ✅ | ✅ | ✅ | (✅) |  |  |
|  |  |  |  |  |  |  |
| **Allowed at Bosch** | ✅ | ❓<br>• no cloud onboarding info | ✅ | ✅ |  |  |
| **Supports all kinds of ML** | n.a. | n.a. | n.a. | n.a. |  |  |
| **Supports on-premise** | ✅ | ❌ | (✅) | ✅ |  |  |
|  |  |  |  |  |  |  |
| **User Experience** | • simple setup with CLI | • intuitive UI | • extensive UI | • intuitive UI |  |  |
| **Maintainability** | • easy for local use<br>• possibly effort for UI (if deployment possible) | • low maintenance (manged service)<br>• still connection to own cloud provider needs to be maintained | • low maintenance (manged service)<br>• depends on setup (if self-hosted) | • depends on setup |  |  |
| **Integration with CI/CD concept** | • integrates with CI/CD (CLI can be used in CI pipeline) | • integrates with CI/CD | • integrates with CI/CD | • integrates with CI/CD |  |  |
| **Reliability & Stability** | • reliable | • enterprise-grade reliable | • enterprise-grade reliable | • reliable |  |  |
| **Modularity & Reusability** | • modular, supports custom plugins | • provides a complete feature platform but can still be used as just a feature store module | • part of bigger tooling platform, modularity as component limited | • modular and reusable, as it is does not replace existing infrastructure and is infrastructure-agnostic |  |  |
| **Performance & Scalability** | • scales with underlying infrastructure | • scalable | • scalable | • scalable |  |  |
|  |  |  |  |  |  |  |
| **Tool already existing at Bosch** | ❓ | ❓ | ❓ | ❓ |  |  |
|  |  |  |  |  |  |  |
| **Decision** | • component has currently only a low priority and will not get considered in the first MLOps pipeline to set up |  |  |  |  |  |
| **Justification** |  |  |  |  |  |  |
| **Decided by** |  |  |  |  |  |  |
| **Date of decision** | <dd.mm.yyyy> |  |  |  |  |  |
| **Comments / Conditions to be met** | <bullet point list, task tracking issues> |  |  |  |  |  |
| **Related Decisions** | <link to related decision> |  |  |  |  |  |

---

**References:**
1. [Springer Chapter on MLOps](https://link.springer.com/chapter/10.1007/978-1-4842-9642-4_4)
2. [DataCamp MLOps Tools](https://www.datacamp.com/blog/top-mlops-tools)
3. [Neptune.ai MLOps Tools Platforms Landscape](https://neptune.ai/blog/mlops-tools-platforms-landscape)
4. [Neptune.ai MLOps Tools Platforms Landscape](https://neptune.ai/blog/mlops-tools-platforms-landscape)y
