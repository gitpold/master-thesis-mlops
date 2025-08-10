# 34 Component - Hyperparameter Tuning

Based on a rapid review of the white and grey literature on MLOps, the following tools were identified for the hyperparameter tuning category:

- Hyperopt
- Optuna
- Ray Tune
- Scikit-Optimize
- SigOpt
- Talos

Since this list of tools is too extensive for a comprehensive evaluation of all entries, the following evaluation is limited to a subset of popular or promising tools.
In addition, some corresponding components of the platforms (if existing) or tools proposed by other means (e.g. by team members) are included in the comparison.

| Name | 34 Component - Hyperparameter Tuning | | | | | |
|------|------|------|------|------|------|------|
| Status | DRAFT | | | | | |
| **Context / Problem / Issue Description** | A crucial aspect of a machine learning project is hyperparameter tuning to optimize model performance. Effective tools for hyperparameter tuning automate the search process, improving efficiency and model accuracy. Here, we compare several hyperparameter tuning tools to identify the best solutions for optimizing ML models. | | | | | |
| **Options considered** | **Option A** | Option B | Option C | Option D | Option E | **Option F** |
| Name & Link | [Optuna](https://optuna.org/) | [Ray Tune](https://docs.ray.io/en/latest/tune/index.html) | [Hyperopt](http://hyperopt.github.io/hyperopt/) | | | |
| Description | An open source hyperparameter optimization framework to automate hyperparameter search | Python library for experiment execution and hyperparameter tuning | Distributed Asynchronous Hyperparameter Optimization in Python | | | |
| License & Cost | • MIT license<br>• free | • MIT license<br>• free | • open source<br>• free | | | |
| Documentation | https://optuna.readthedocs.io/en/stable/index.html | https://docs.ray.io/en/latest/tune/index.html | http://hyperopt.github.io/hyperopt/ | | | |
| Infrastructure / How to run it | • Python library, can be installed via PIP<br>• dashboard available to run locally (via Python or Docker) or as extension in VS code or Jupyter Lab | • Python library, can be installed via PIP | • Python library, can be installed via PIP | | | |
| **Academia** | | | | | | |
| Advantages | • supports various optimization algorithms ¹ ²<br>• provides a user-friendly interface for defining search spaces and objective functions ¹<br>• distributed optimization and handling large datasets ³ ²<br>• uses GPU ³<br>• provides User API to dynamically build search spaces ⁴ | • distributed optimization and handling large datasets ³<br>• uses GPU ³ | • provides a simple interface for defining search spaces and objective functions ¹<br>• suitable for optimizing complex hyperparameter configurations ¹<br>• distributed optimization and handling large datasets ³<br>• designed to accommodate Bayesian optimisation algorithms ⁴ | | | |
| Disadvantages | | | • missing some documentation ⁴ | | | |
| **Requirements** | | | | | | |
| Compatibility with Azure | n.a. | n.a. | n.a. | | | |
| Compatibility with GitHub | n.a. | n.a. | n.a. | | | |
| No own Kubernetes needed | n.a. | n.a. | n.a. | | | |
| | | | | | | |
| Allowed at Bosch | ✅ | ✅ | ✅ | | | |
| Supports all kinds of ML | ❌ only for classical ML | ❌ only for classical ML | ❌ only for classical ML | | | |
| Supports on-premise | n.a. | n.a. | n.a. | | | |
| | | | | | | |
| User Experience | • good API<br>• good documentation | • integrates with Ray ecosystem | • simple API | | | |
| Maintainability | • easy to maintain<br>• minimal setup | • easy to maintain<br>• benefits from Rays scalability | • easy to maintain<br>• minimal setup | | | |
| Integration with CI/CD concept | • integrates with CI/CD | • integrates with CI/CD<br>• works well with Ray | • integrates with CI/CD | | | |
| Reliability & Stability | • reliable, growing community support | • reliable, backed by Ray | • reliable, mature | | | |
| Modularity & Reusability | • modular, supports multiple ML frameworks | • modular, supports multiple ML frameworks | • modular, supports multiple ML frameworks | | | |
| Performance & Scalability | • high performance, scales with distributed setups | • high performance, highly scalable with Ray clusters | • good performance | | | |
| | | | | | | |
| Tool already existing at Bosch | ❓ | ❓ | ❓ | | | |
| | | | | | | |
| **Decision** | • component has currently only a medium priority and will not get considered in the first MLOps pipeline to set up<br>• further, there should be no big differences between each option as well as no dependencies to other components → any of these tools could be used based on individual project requirements | | | | | |
| Justification | | | | | | |
| Decided by | | | | | | |
| Date of decision | <[dd.mm](http://dd.mm).yyyy> | | | | | |
| Comments / Conditions to be met | <bullet point list, task tracking issues> | | | | | |
| Related Decisions | <link to related decision> | | | | | |

## References

1. https://neptune.ai/blog/mlops-tools-platforms-landscape
2. https://www.projectpro.io/article/best-mlops-tools-/574
3. https://www.xenonstack.com/blog/mlops-tools
4. https://ieeexplore.ieee.org/document/9792270
