# 10 Architecture - Staging Concept

| Field | Details |
|-------|---------|
| **Name** | 10 Architecture - Staging Concept |
| **Status** | DRAFT |
| **Context / Problem / Issue Description** | As in application development, it is important to have a staging concept in machine learning model development so that changes can be tested and validated before going live. However, when developing ML models, there are different ways to implement such a staging concept. |

## Options Comparison

| Criteria | Option A: Deploy Models | Option B: Deploy Code |
|----------|------------------------|----------------------|
| **Name** | Deploy Models | Deploy Code |
| **Description** | ![Option A Diagram] | ![Option B Diagram] |
| **Academia** |  |  |
| **Advantages** | • simpler handoff for data scientist<br>• only need to train the model once (easier to manage, cheaper in case model training is expensive) | • access control to data is possible (different data on dev than prod)<br>• easier and safer to setup automated retraining<br>• ancillary code can follow the same staging pattern as the model training code |
| **Disadvantages** | • not possible if production data is not accessible form development environment<br>• automated model retraining not supported (only via dev environment)<br>• requires a separate code deployment path (as this is still needed for production stage) | • data scientists have steeper learning curve for handing off<br>• data scientists need visibility into training results from prod environment |
| **Requirements** |  |  |
| **Compatibility with Azure** | n.a. | n.a. |
| **Compatibility with GitHub** | n.a. | n.a. |
| **No own Kubernetes needed** | n.a. | n.a. |
| **Allowed at Bosch** | n.a. | n.a. |
| **Supports all kinds of ML** | • potentially easier/cheaper for big models with huge training costs (Deep Learning models, training LLMs) | • potentially more expensive for big models with huge training costs (Deep Learning models, training LLMs) |
| **Supports on-premise** | n.a. | n.a. |
| **User Experience** | • easier handoff, no need to provide model training code | • need to provide model training code<br>• but easier once everything is set up |
| **Maintainability** | • no need to maintain model training code propagation<br>• harder to maintain model itself as retraining only possible in dev | • need to maintain model training code<br>• maintaining model versions way easier |
| **Integration with CI/CD concept** | • model training code only in dev stage, afterwards no staging so no integration necessary | • easier integration with existing CI/CD concept as model training code follows same process as all other code |
| **Reliability & Stability** | • less components<br>• exact model has already been tested on dev before being deployed to production | • more stable process<br>• if model trained with different data on production, possibly different performance than on dev |
| **Modularity & Reusability** | • model training code only done one dev, not reused | • model training code propagated to different stages, could get reused in other projects |
| **Performance & Scalability** | • easy solution but might not scale with many projects (because of need to always train models on dev) | • initially more effort but scales better with more (old) projects as retraining can be done (possibly automatic) on prd |
| **Tool already existing at Bosch** | n.a. | n.a. |

## Decision

| Field | Value |
|-------|-------|
| **Decision** |  |
| **Justification** |  |
| **Decided by** |  |
| **Date of decision** | <dd.mm.yyyy> |
| **Comments / Conditions to be met** | <bullet point list, task tracking issues> |
| **Related Decisions** | <link to related decision> |

---

**References:**
1. [The Big Book of MLOps (Databricks, v6, 2022)](https://blog.infocruncher.com/resources/ml-productionisation/The%20Big%20Book%20of%20MLOps%20(Databricks,%20v6,%202022).pdf)
