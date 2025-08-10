# 11 Architecture - Platform vs Tools

| | |
|---|---|
| **Name** | **11 Architecture - Platform vs Tools** |
| **Status** | **DECIDED** |
| **Context / Problem / Issue Description** | When designing an MLOps solution there is the division between buying/choosing a complete platform and potentially patching this solution with some tools or assembling a platform on your own from the wide range of available MLOps tools. |


| **Options considered** | **Option A** | **Option B** | **Option C** |
| --- | --- | --- | --- |
| **Name** | All-in-on platform | Platform extended by single tools | Combination of single tools |
| **Description** | One complete MLOps platform that provides all necessary functionality | One main MLOps platform that provides the main functionality but extended by single tools (that provide a better solution than the platform for this component) | Completely piecing together a MLOps solution from single different tools using the most suitable tool for each component |
| **Academia** | | | |
| **Advantages** | • good option to model a standard process without customizations ¹ | • provides better flexibility and an effective solution for a task with unique characteristics² | • provides better flexibility and an effective solution for a task with unique characteristics²<br>• most flexible solution with the possibility to solve any future needs ¹ |
| **Disadvantages** | • new needed features might be hard to add in time if not already existing in platform ¹ | • with more tools it is harder to achieve compatibility between all tools ² | • with more tools it is harder to achieve compatibility between all tools ²<br>• probably requires specialists and trained teams to build and maintain an MLOps platform ¹ |
| **Requirements** | | | |
| **Compatibility with Azure** | • depending on platform | • depending on platform and tools | • depending on tools but probably yes |
| **Compatibility with GitHub** | • depending on platform | • depending on platform and tools | • depending on tools |
| **No own Kubernetes needed** | • depending on platform | • depending on platform and tools | • depending on tools |
| | | | |
| **Supports all kinds of ML** | • depending on platform | • depending on platform and tools | • depending on tools |
| **Supports on-premise** | • depending on platform | • depending on platform and tools | • depending on tools |
| | | | |
| **User Experience** | • users need to understand/learn only one platform<br>• platform should provide a good integration between components | • users need to understand/learn one platform and some tools<br>• platform should provide a good integration between its components<br>• complicated or lacking parts can be extended by easy-to-use single tools | • users need to understand/learn multiple different tools<br>• for each component an easy-to-use tool can get selected<br>• integrations between different tools will tend to be lacking or needing manual effort |
| **Maintainability** | • depending on platform but only one tool to maintain | • depending on platform and tools but only one platform and small amount of additional tools to maintain | • depending on tools but potentially high amount of different tools to maintain |
| **Integration with CI/CD concept** | • depending on platform | • depending on platform and tools | • depending on tools |
| **Reliability & Stability** | • depending on platform but generally using one platform should at least provide reliability and stability on the connection between the different components | • depending on platform and tools | • depending on tools and the integrations between them but potentially higher risk of problems between components |
| **Modularity & Reusability** | • not much modularity and only reusability of process as a whole | • some modularity and reusability, probably mainly for components extended by single tools | • high modularity because of different tools for every component<br>• potentially less reusability of process as a whole but high reusability for single components |
| **Performance & Scalability** | • depending on platform | • depending on platform and tools | • depending on tools |


| **Decision** | **Option B:** Platform extended by tools |
|-------|-------|
| **Justification** | • provides a good balance between maintainability because mostly one platform needs to be operated and an effective solution as single tools can add or extend needed functionality missing with the platform |
| **Decided by** | |
| **Date of decision** | 31.07.24 |
| **Comments / Conditions to be met** | |
| **Related Decisions** | |

1. https://dzone.com/articles/mlops-architectural-models-advanced-guide
2. https://ieeexplore.ieee.org/document/9720902
