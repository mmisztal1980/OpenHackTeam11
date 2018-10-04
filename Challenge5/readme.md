#Challenge 5

## Implement a basic Blue/Green deployment strategy
In the previous challenges, your team has implemented a pipeline that implements Continuous Integration, Unit Testing and Continuous Deployment however your deployment mechanism may require downtime that can interfere with the functionality of the application and services that depend on it. Rollback is another consideration during deployment should the deployment encounter issues.

You will now implement a Blue/Green deployment mechanism for your APIs that aims to eliminate downtime while allowing for ease of rollback.

## Challenge
With the tooling that you have selected previously, your challenge is to update your pipeline to perform Blue/Green deployment automatically.

Some understanding of Kubernetes and the ingress controller will be needed for this challenge, refer to the links provided to get a better understanding of Blue/Green deployment with Kubernetes. We have selected Traefik to be the ingress controller for this environment, the logic that you will implement applies to other ingress controllers on Kubernetes.

It is recommended to think about your strategy as a team before you start coding.

From now downtime in the deployment does count against your score.

## Success Criteria
Explain to your proctor the logic that you have implemented for blue/green deployment and explicitly address the following points: - How do you know that the new container of your API is ready? - How do you define what is your targeted environment? - When do you delete the previous version of your API?

Demonstrate that a code change in your API is deployed initially to an environment and automatically switched to a new one with no downtime for this API.

Demonstrate a simple decision point to close out the release or rollback in your pipeline.

Demonstrate you can roll back to the previous version. Teams can rollback via pipeline automation or from cmd line issuing cmds with Helm or Kubectl.

STRETCH GOAL: Roll back your deployment using automation in your pipeline to detect deployment state and take action.

To successfully complete the challenge, it is expected to implement the strategy for at least one API. Bonus points will be credited for the support of additional APIs. You proctor will give you a change to push through your pipeline to test your strategy.

## References
- [Blue/Green deployment](https://martinfowler.com/bliki/BlueGreenDeployment.html)
- [Configuring your release pipelines for safe deployments](https://blogs.msdn.microsoft.com/devops/2017/04/24/configuring-your-release-pipelines-for-safe-deployments/)

### Platform related content
- [Sample Blue/Green strategy using Kubernetes](https://github.com/ContainerSolutions/k8s-deployment-strategies/tree/master/blue-green)
- [Path based routing with Traefik](https://docs.traefik.io/user-guide/kubernetes/#path-based-routing)
- [Liveness and Readiness probes on Kubernetes](https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-probes/#define-readiness-probes)
- [Perform Rolling Update Using a Replication Controller](https://kubernetes.io/docs/tasks/run-application/rolling-update-replication-controller/)
- [Kubernetes deployment rollingUpdate max-Unavailable strategy](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/#max-unavailable)
- [Kubernetes replica set revision history](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/#revision-history-limit)

### Azure DevOps specific content
- [Defining custom variables in Azure DevOps](https://docs.microsoft.com/en-us/azure/devops/pipelines/release/variables?view=vsts&tabs=shell#set-in-script).
- [Using Variable Groups in Azure DevOps](https://docs.microsoft.com/en-us/azure/devops/pipelines/library/variable-groups?view=vsts)
- [Azure DevOps - Conditional Release Flow](https://blogs.msdn.microsoft.com/ukhybridcloud/2018/04/29/azure-devops-use-vsts-conditions-to-control-build-or-release-flow/)

### How to run Helm command from the CLI.

Get kube config to a known location
```bash
echo "Get kubeconfig file"
az aks get-credentials --resource-group <resource group name> --name <aks cluster name> --file $(System.DefaultWorkingDirectory)/kubeconfig
```
Using variable groups across jobs
The ability to set a variable like indicated on [this page](https://docs.microsoft.com/en-us/azure/devops/pipelines/release/variables?view=vsts&tabs=shell#set-in-script) is limited to a given stage in the release pipeline.

If want to use a variable across different release stages you will have to use variable groups. To set a variable in a variable group, you will have to use the REST API as indicated [here](https://docs.microsoft.com/en-us/rest/api/vsts/distributedtask/variablegroups/update?view=vsts-rest-4.1). Below is a sample code:

```bash
curl -X PUT -H "Content-Type: application/json" -H "Authorization: Bearer $(System.AccessToken)" -d '{ "variables": { "TargetEnvironment": { "value": "'"$myvar"'" } }, "type": "Vsts", "name": "BlueGreenVars" }' "https://dev.azure.com/<AzureDevOps_Workspace>/<AzureDevOps_Project>/_apis/distributedtask/variablegroups/<VariableGroupIndex>?api-version=4.1-preview.1"
```

In order to make this work, you also need to give admin permission to “Project Collection Build Service” on the variable group that will hold this variable and enable “Allow Access to OAuth Token on the property of the Agent Job”.