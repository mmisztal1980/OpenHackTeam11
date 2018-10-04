# Challenge 3

## Implement Unit Testing
Regardless how carefully you write your code, it is a best practice to run automated tests against it before it gets deployed and ensure that the maximum of your code is covered with unit tests.

## Challenge
You are expected to improve the pipeline that you have started to build in the previous challenge by validating the functionality of at least one part of the code for each of the APIs of your application.

In the eventually of a test failure, a bug shall be created automatically and added in the backlog and the submitted changes are not integrated in your code.

You are also expected to be able to report on the code coverage of your unit tests and fail a build if a code coverage is not sufficient.

**Reminders:** - The code for each of the APIs is located on the following repo: https://github.com/Azure-Samples/openhack-devops-team/tree/master/apis - During this challenge, you are expected to focus exclusively on Unit Tests.

## Success Criteria
Walk your proctor through the implementation of the tests that you have done and the branch policy that you have implemented.

- Your proctor will give you a change to submit through your pipeline. You will have to demonstrate that your pipeline is running the tests against the code. If the test does not complete successfully, show that an issue has been created in the team’s backlog.

- Your pipeline should have a gate that will report when a build does not meet a certain level of code coverage. Show to your proctor how you have implemented this functionality in your pipeline.

> NOTE: If using SonarCloud, it is advisable you create a new pipeline based on one of the SonarCloud templates and add your build/deploy steps instead of trying to add SonarCloud into your existing pipeline.

## References and further reading

### Branch policies
A [cheat sheet](https://openhacks.azurewebsites.net/Overview) for the DevOps OpenHack is available at the end of the Overview page.

- [Azure DevOps branch policies](https://docs.microsoft.com/en-us/azure/devops/repos/git/branch-policies?view=vsts)
- [GitHub - About protected Branches](https://help.github.com/articles/about-protected-branches/)

### Unit testing
- [Writing and running unit test with GoLang](https://blog.alexellis.io/golang-writing-unit-tests/)
- [Writing and running unit test with Node.JS](https://blog.risingstack.com/node-hero-node-js-unit-testing-tutorial/)
- [Writing and running unit test with .Net Core](https://docs.microsoft.com/en-us/dotnet/core/testing/unit-testing-with-dotnet-test?view=aspnetcore-2.1)
- [Writing and running unit test with Java](http://www.vogella.com/tutorials/Mockito/article.html)

### Code Coverage (possible options)
- [Integrate Visual Studio Team Services with SonarCloud](https://docs.microsoft.com/en-us/labs/devops/sonarcloudlab/index)
- [SonarCloud documentation for VSTS](https://sonarcloud.io/documentation/integrations/vsts)
- [Using SonarCloud in a VSTS pipeline](https://docs.sonarqube.org/display/SCAN/Analyzing+with+SonarQube+Extension+for+VSTS-TFS)
- [CoverAlls](https://coveralls.io/)
- [CodeCov](https://codecov.io/)
- [Jacoco](https://www.jacoco.org/jacoco/)

### Further reading on Test Driven Development
- [Test Driven Development Essay](http://agiledata.org/essays/tdd.html)