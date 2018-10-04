# Challenge 7

## Implement Integration and Load testing
In your second challenge, you have improved your initial pipeline to perform at least one unit tests for each API of the MyDrivving application. Your boss is nervous that despites the effort that you have put in the creation of the unit tests for each API, you may not catch certain problems related to their integration.

## Challenge
In this challenge you are asked to improve your pipeline to support at least one integration test. You are free to build the integration test of your choice using the language and framework of your choice. Should a problem occur during the execution of the integration test, the version shall not be deployed into production.

The integration of updated components can reveal performance issues. In this challenge you want to also address this type of problems and avoid the deployment in production of a version of your application that does not meet your performance baseline. Your challenge is to add to your pipeline a load test simulation that will complement your integration tests. You have to target the same API.

The downtime in the deployment does count against your score.

## Success Criteria
Submit an update to your application to demonstrate the implementation of the integration test of your choice and load tests into your pipeline.

Your must include your integration tests as a step in your pipeline and the process shall be halted in the case the integration test fails. Explain to your proctor the choice that you have made regarding the phase of your pipeline that runs the tests.

Your load test must be fully integrated in your pipeline and the process shall be halted in the case a performance degradation is observed.

## References
- [Integration test with .Net Core](https://docs.microsoft.com/en-us/aspnet/core/test/integration-tests?view=aspnetcore-2.1)
- [Integration testing in GO](https://blog.codeship.com/testing-in-go/)
- [Integration testing with Node.JS](https://www.codementor.io/olatundegaruba/integration-testing-supertest-mocha-chai-6zbh6sefz)

## Further Reading
- [Integration testing](http://softwaretestingfundamentals.com/integration-testing/)
- [Integration tests vs Unit tests](https://www.guru99.com/unit-test-vs-integration-test.html)