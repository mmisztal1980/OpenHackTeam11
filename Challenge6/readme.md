# Challenge 6

## Implement a monitoring solution for your MyDriving APIs
With a functional pipeline that builds and deploys your APIs, your next step is to focus on the health and performance of your APIs. Your challenge is to define and implement a monitoring strategy for your APIs.

## Challenge
In this challenge, carefully select the monitoring tool(s) that you want to use to achieve this challenge.

You are expected to achieve the following goals:

- Implement a solution that monitors the health and performance of your APIs. You will have to collect data regarding the performance of the cluster and the APIs.
- Define the performance baseline for the APIs running on your cluster and implement a mechanism that will automatically create an incident in your work item tracking system if the requests response time increase by more than 20%.
- Build a dashboard that will allow you to visualize the global health of your environment.

> NOTE: It is recommended to discuss the capabilities of the tools that you have selected with your team. Keep in mind that your proctor is here to help you make an educated choice.

The downtime in the deployment does count against your score.

## Success Criteria
Show to your proctor the aggregated view your application and infrastructure.

Cluster monitoring: For example CPU usage, disk space on the nodes, etc.
Ability to execute actions in the case an alert is raised
And pick one of either (or stretch goal for both): - APIs monitoring: For example response time for one of the four APIs (Trips, POI, Users, User, UserProfile) - SQL database monitoring: percentage of % of DTU

Show to your proctor that an incident is automatically created when an alert is raised.

## References

### Azure solutions 
- [Overview of the Azure Monitoring solutions](https://docs.microsoft.com/en-us/azure/monitoring-and-diagnostics/monitoring-overview)
- [Azure Monitor](https://docs.microsoft.com/en-us/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)
- [Azure Application Insights](https://docs.microsoft.com/en-us/azure/application-insights/)
- [Azure SQL Analytics](https://aka.ms/sqlazureonboarding)

### Kubernetes solutions 
- [Azure Kubernetes Service (AKS) container health monitoring](https://docs.microsoft.com/en-us/azure/monitoring/monitoring-container-health)
- [Prometheus](https://github.com/kubernetes/charts/tree/master/stable/prometheus), [Prometheus Operator](https://github.com/coreos/prometheus-operator/blob/1fe9016e70e8319032ede49ee68d43693f01b0e6/contrib/kube-prometheus/README.md)
- [DataDog](https://www.datadoghq.com/blog/monitoring-kubernetes-with-datadog/)
> Note: you may have to open a trial subscription to use DataDog.
- [SysDig](https://sysdig.com/blog/monitoring-kubernetes-with-sysdig-cloud/)
> Note: you may have to open a trial subscription to use SysDig.
