# 36 Component - Model Testing & Validation

Based on a rapid review of the white and grey literature on MLOps, the following tools were identified for the model testing & validation category:

- Alibi Explain
- Arize Phoenix
- Deepchecks
- Fiddler
- Great Expectations
- TruEra

Since this list of tools is too extensive for a comprehensive evaluation of all entries, the following evaluation is limited to a subset of popular or promising tools.
In addition, some corresponding components of the platforms (if existing) or tools proposed by other means (e.g. by team members) are included in the comparison.

- Giskard
- Galileo
- Ragas

| Name | 36 Component - Model Testing & Validation | | | | | | | |
|------|------|------|------|------|------|------|------|------|
| Status | DRAFT | | | | | | | |
| **Context / Problem / Issue Description** | A critical part of a machine learning project is model testing and validation to ensure models perform as expected. This includes testing for classical ML models, as well as large language models (LLMs) and retrieval-augmented generation (RAG) systems. Here, we compare various tools for model testing and validation to ensure robust and reliable model performance across different types of ML systems. | | | | | | | |
| **Options considered** | **Option A** | Option B | Option C | Option D | Option E | Option F | Option G | **Option H** |
| Name & Link | [Alibi Explain](https://www.seldon.io/solutions/alibi) | [Arize Phoenix](https://phoenix.arize.com/) | [Deepchecks](https://deepchecks.com/) | [Fiddler](https://www.fiddler.ai) | [Great Expectations](https://greatexpectations.io/) | [Giskard](https://www.giskard.ai/) | [Galileo](https://www.rungalileo.io/) | [Ragas](https://docs.ragas.io/en/stable/) |
| Description | Python library aimed at machine learning model inspection and interpretation | Observability library designed for experimentation, evaluation, and troubleshooting | Holistic open-source solution for all of your AI & ML validation needs | Enterprise AI observability tool that includes model performance monitoring, explainability, and validation tools | Tool for data validation, documentation, and profiling | Holistic Testing platform for AI models to control all 3 types of AI risks: Quality, Security & Compliance | Generative AI Evaluation & Observability Stack | A framework that helps you evaluate your Retrieval Augmented Generation (RAG) pipelines |
| License & Cost | • BSL<br>• free | • Elastic License 2.0<br>• free | • AGPL 3.0<br>• free<br>• additional product for LLM evaluation as proprietary, paid managed service | • proprietary<br>• paid (different pricing tiers) | • Apache 2.0<br>• free<br>• managed service with different pricing tiers available | • Apache 2.0<br>• free open source version<br>• paid enterprise version | • proprietary<br>• paid | • Apache 2.0<br>• free |
| Documentation | https://docs.seldon.io/projects/alibi/en/stable/ | https://docs.arize.com/phoenix | https://docs.deepchecks.com/stable/getting-started/welcome.html | https://docs.fiddler.ai/ | https://docs.greatexpectations.io/docs/home/ | https://docs.giskard.ai/en/stable/getting_started/quickstart/index.html | https://docs.rungalileo.io/galileo | https://docs.ragas.io/en/stable/ |
| Infrastructure / How to run it | • Python package, can be installed via PIP | • Python package, can be installed via PIP<br>• self-hosting on-premise or with cloud provider possible<br>• either via Docker or to Kubernetes (manifest files or Kustomize)<br>• needs a database | • Python package, can be installed via PIP | • managed cloud version<br>• self-hosting on-premise or with cloud provider via Helm Chart on Kubernetes possible (very complex Helm Chart, many dependencies) | • Python package, can be installed via PIP<br>• managed cloud service available | • Python package, can be installed via PIP<br>• enterprise version can be deployed via Docker on-premise or to cloud infrastructure (AWS, Azure, GCP, Hugging Face) | • can be deployed to Kubernetes on-premise or to cloud infrastructure (AWS, Azure, GCP, ...)<br>• needs a PostgreSQL database<br>• needs S3 compatible storage | • Python package, can be installed via PIP |
| **Academia** | | | | | | | | |
| Advantages | • explanation methods for both classification and regression models ¹ | | • minimal effort ²<br>• strong and active community ¹ | • easy-to-use, clear UI ³<br>• variety of tools for explaining model predictions ² | • user-friendly documentation ¹ | | | |
| Disadvantages | | | | | • not for model testing, only for data testing ⁴ ² | | | |
| **Requirements** | | | | | | | | |
| Compatibility with Azure | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Compatibility with GitHub | n.a. | n.a. | n.a. | n.a. | n.a. | n.a. | n.a. | n.a. |
| No own Kubernetes needed | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ✅ |
| | | | | | | | | |
| Allowed at Bosch | ✅ | ✅ | ✅ | ❓<br>• no cloud onboarding information | ✅ | ✅ | ❓<br>• no cloud onboarding information | ✅ |
| Supports all kinds of ML | (✅) very limited for LLMs | (✅) focus on LLMs and NLP | ❌ for tabular, NLP, and CV data (for LLMs there is a separate, paid Deepchecks LLM Evaluation tool) | ✅ | ❌ not for model, but for data testing | ❌ for LLMs, RAGs | ❌ for LLMs, RAGs | ❌ for LLMs, RAGs |
| Supports on-premise | ✅ | ✅ | ✅ | (✅) | (✅) | ✅ | ✅ | ✅ |
| | | | | | | | | |
| User Experience | • no UI<br>• comprehensive, but a bit complex documentation | • intuitive UI | • UI only via separate, open-source Deepchecks Monitoring tool<br>• extensive documentation | • intuitive UI | • no UI for free version | • free version results as static page (paid version more extensive UI) | • intuitive UI | • no UI<br>• good documentation |
| Maintainability | • easy to maintain, minimal local setup | • depending on setup<br>• for local version low maintenance effort<br>• for self-hosted version some maintenance effort | • easy to maintain, minimal local setup<br>• for potential monitoring tool some setup and maintenance effort for self-hosting | • depending on setup<br>• low maintenance for managed service<br>• high maintenance effort for self-hosting | • local version requires some setup | • depending on setup<br>• free version with local setup is easy to maintain | • low maintenance (managed service) | • easy to maintain, minimal setup |
| Integration with CI/CD concept | • integrates with CI/CD | • integrates with CI/CD | • integrates with CI/CD | • integrates with CI/CD | • integrates with CI/CD | • integrates with CI/CD, for example GitHub Actions | • integrates with CI/CD | • integrates with CI/CD |
| Reliability & Stability | • reliable, mature | • reliable | • reliable, growing community support | • reliable, enterprise | • reliable, mature | • reliable | • reliable | • reliable, newer |
| Modularity & Reusability | • modular, integrates with various ML frameworks | • modular, integrates with various ML frameworks | • modular, integrates with various ML frameworks | • modular, integrates with various ML frameworks | • modular, integrates with different ML frameworks | • modular, integrates with various ML frameworks | • modular, integrates with various ML frameworks | • modular, integrates with various ML frameworks |
| Performance & Scalability | • good performance | • high performance | • good performance | • high performance | • good performance | • good performance | • high performance | • good performance |
| | | | | | | | | |
| Tool already existing at Bosch | ❓ | ✅ | ✅ | ❓ | ❓ | ❓ | ✅ | ✅ |
| | | | | | | | | |
| **Decision** | • Ragas, Giskard or Arize Phoenix for LLM/RAG<br>• possibly Alibi Explain or Deepchecks for classical ML testing (if platform provides not enough features yet) | | | | | | | |
| Justification | • Fiddler is dropped as there is no cloud onboarding information for the managed service and the on-premise installation would need a Kubernetes cluster (as well as as a paid license)<br>• Galileo is dropped as there is no cloud onboarding information for the managed service (although there has been a POC and talks with the provider by BD) and the on-premise installation would need a Kubernetes cluster (as well as as a paid license)<br>• Great Expectations is excluded as it does not provide model testing, but data testing. This could be relevant as an additional feature, but is not considered further here<br>• Alibi Explain and Deepchecks are libraries for evaluation of classical ML models and could be used without much effort and dependencies. Depending on the featureset of the platform these could get used<br>• Arize Phoenix, Giskard and Ragas provide solutions for testing of LLM/RAG systems. As the featureset of both platforms is not as complete in this regard (yet), it would make sense to additionally use one of these tools | | | | | | | |
| Decided by | | | | | | | | |
| Date of decision | <[dd.mm](http://dd.mm).yyyy> | | | | | | | |
| Comments / Conditions to be met | <bullet point list, task tracking issues> | | | | | | | |
| Related Decisions | <link to related decision> | | | | | | | |

## References

1. https://neptune.ai/blog/best-open-source-mlops-tools
2. https://neptune.ai/blog/mlops-tools-platforms-landscape
3. https://www.datacamp.com/blog/top-mlops-tools
4. https://ieeexplore.ieee.org/document/10172734
