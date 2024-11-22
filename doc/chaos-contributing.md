# Chaos Experiment Contribution

We welcome contributions to the chaos experiment collection. Please keep in mind the guidelines outlined in this document when creating PRs with experiments.

## Guidelines

- Keep in mind that Chaos Engineering is not about randomly breaking stuff. It's part of an experimentation cycle, that aims to improve overall solution reliability: For a component, a failure mode is identified. A mitigation is determined for that specific failure mode, after which an experiment is designed to validate that that mitigation has been implemented correctly by introducing that failure into the solution. For each experiment that we adopt into the collection, we want to see that process described (e.g. in the comments of the experiment bicep). 

- Chaos experiments should (where feasible) be contained in a single Bicep file. This makes it easier to add and remove experiments to the repo and easier for people to pick out a specific experiment for use in their own environment.

- Please use extensive commenting in the definition of a chaos experiment