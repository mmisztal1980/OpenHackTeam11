# Challenge 2

## Implement Continuous Integration - CI
Reminder: The credentials you need to access the Azure subscription assigned to your team are available on the OpenHack portal [https://openhacks.azurewebsites.net/](https://openhacks.azurewebsites.net/).

Prior to the event, a Kubernetes cluster using Azure Kubernetes Service (AKS) has been provisioned for you. The 4 APIs of the MyDriving service have already been deployed and configured on this cluster.

The code and tests for the APIs is available in the following repository: [https://github.com/Azure-Samples/openhack-devops-team/tree/master/apis](https://github.com/Azure-Samples/openhack-devops-team/tree/master/apis)

Before you joined the event, each API of the MyDriving application was built and deployed using the following scripts:

- [POI API deployment script](https://github.com/Azure-Samples/openhack-devops-proctor/blob/master/provision-team/build_deploy_poi.sh)
- [Trips API deployment script](https://github.com/Azure-Samples/openhack-devops-proctor/blob/master/provision-team/build_deploy_trip.sh)
- [Users API deployment script](https://github.com/Azure-Samples/openhack-devops-proctor/blob/master/provision-team/build_deploy_user.sh)
- [Userprofile API deployment script](https://github.com/Azure-Samples/openhack-devops-proctor/blob/master/provision-team/build_deploy_user-java.sh) 
  - NOTE: The [traefik dashboard](https://openhacks.azurewebsites.net/Overview) provides valuable information for the services deployed in your cluster.

At this point, downtime in the deployment does not count against your team.

## Challenge
NOTE: The following tools have been tested with this challenge: - Orchestrators - [Azure DevOps](https://azure.microsoft.com/en-us/services/devops/) - Formerly known as Visual Studio Team Services (VSTS) - [Jenkins](https://jenkins.io/). You may use any other set of tools however the proctors will only be able to provide limited guidance. - Version Control - GitHub - Azure DevOps - Repos . Formerly known as VSTS Git

If your team is planning to use Jenkins, a Jenkins master virtual machine has been provisioned in your subscription, refer to the cheat sheet how to connect to the Jenkins VM.

Select the tooling that best fits your team’s skills or learning plans, and implement the part of your pipeline that builds your application and pushes the container image to a registry. You are not expected to deploy any resources at this time.

Create your own code repository either by forking the provided repo on Github or clone into Azure Repos. Your pipeline should automatically make a link between a given build and its corresponding work items. You are expected to work on all the APIs of the MyDriving application.

> NOTE: In Azure DevOps you can create the pipeline in YAML if you desire but we strongly recommend you start by using the [visual designer](https://docs.microsoft.com/en-us/azure/devops/pipelines/get-started-designer?view=vsts&tabs=new-nav).

You are expected to implement a policy so that any code change submitted must go through a peer review and formal approval process.

> NOTE: Your team should be able to complete all challenges without needing to modify the API code. There is one exception where you may need to introduce a change to trigger an automated pipeline. Talk to your proctor when you get to this step if you need help finding an easy change to make._

## Success Criteria
Show to your proctor that you can link a work item with the associated code changes and the artifacts that have been generated.

Demonstrate to your proctor that you have implemented a policy to prevent any unreviewed code changes.

> NOTE: While the application is running in a Kubernetes cluster, the focus of this event is implementing DevOps practices. Treat the underlying Kubernetes infrastructure as a black box. Feel free to reach out to your proctor if you have any issues about containers, Kubernetes, Helm etc.

## References
- A [cheat sheet](https://openhacks.azurewebsites.net/Overview) for the DevOps OpenHack is available at the end of the Overview page.

> NOTE: CI which uses best practices includes automated testing and ideally trunk-based development. Automated testing will be covered later and will extend the CI setup completed here.

- Continuous Integration [Sam Guckenheimer’s very brief definition](https://docs.microsoft.com/en-us/azure/devops/learn/what-is-continuous-integration)
- Continuous Integration [Martin Fowler’s longer definition](https://martinfowler.com/articles/continuousIntegration.html) - Although the definition is from 2006, the practices and concepts are still valid. Parts of this definition have now been broken down into other DevOps practices such as continuous deployment & release management.

### Jenkins related content
The recommendation is to use the [Kubernetes plugin](https://jenkins.io/doc/pipeline/steps/kubernetes/) to build the pipeline as code.
[Documentation for creating a Jenkins pipeline](https://jenkins.io/doc/book/pipeline/) and a [sample Jenkins pipeline](https://github.com/dtzar/Jenkins-Packer-Terraform/blob/master/Jenkinsfile).