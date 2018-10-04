# Challenge 8

## Implement phased rollout with rollback
The executive committee is nervous with any upcoming change and they want to be able to validate the changes on a small subset of your customers before doing a full deployment into production.

## Challenge
Your challenge is to implement a solution that enables the phased rollout (percentage based) of a new version of the API of your choice. The implementation of the mechanism for all APIs will grant bonus points.

Revise, if needed, your deployment strategy regarding how you will perform the phased update of each APIs on your cluster. It may be a good idea to step back and look at the overall strategy at this point.

Update your pipeline to implement a mechanism so that your users are gradually switched to the new version of the application while monitoring the health of the new version of the API. The flow along the pipeline should include at least one manual approval and one fully automated step.

Your new pipeline shall include the ability to roll back to the previous version if an issue is detected during the phased rollout of the new version. At each step, if an issue is detected, your release automation should create an issue in your backlog.

The downtime in the deployment does count against your score.

## Success Criteria
Explain to your proctor your updated strategy and the associated technical details.

Demonstrate to your proctor that a change in the code of your chosen APIs is deployed with a phased rollout. Walk through each phase of your process and explain the state of your deployment.

Demonstrate your ability to automatically rollback to the previous stable version and the creation of the associated issue in your backlog.

STRETCH GOAL: If you previously implemented challenge 6, automate your rollback based on monitoring the environment.

## Reference
- [Traffic management with Istio](https://istio.io/docs/concepts/traffic-management/)
- [Traefik traffic splitting](https://docs.traefik.io/user-guide/kubernetes/#traffic-splitting)