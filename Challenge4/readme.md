# Challenge 4

## Implement Continuous Deployment - CD
After Continuous Integration has completed successfully, you should deploy automatically the updated version of the application to your cluster.

You are expected to be able to correlate the changes made in the code with the corresponding release.

## Challenge
> NOTE 1: Helm version 2.10.0 has already been installed on your cluster. 

> NOTE 2: At this point, application downtime does not count against your score.

By using the tooling that you have selected previously, your challenge is to refer to the flow that you have defined in the first and second challenges and add continuous deployment capabilities to your existing pipeline.

Azure DevOps has a bug in the helm template, see this [community post](https://developercommunity.visualstudio.com/content/problem/324154/error-endpoint-auth-data-not-present.html) for guidance

## Success Criteria
Your proctor will provide you with an update to perform to your application. You will need to be able to demonstrate that you can reference the deployment of this feature with its corresponding work items. Your branch/pull request policy can be used to enforce workflow and gates between CI and CD activities.

## Platform related content
- The Illustrated Children’s Guide to Kubernetes
- What is Helm?
- Deploying an application on Kubernetes with Helm
- Passing values to a helm chart

## References
- Deploy an application to Kubernetes from Azure DevOps