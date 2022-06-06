# Automated Testing Test

Automated testing is the application of software tools to automate a human-driven manual process of reviewing and validating a software product. Most modern agile software projects now include automated testing from inception.

## Why is testing automation important to continuous delivery? <a href="#why-is-testing-automation-important-to-continuous-delivery" id="why-is-testing-automation-important-to-continuous-delivery"></a>

Continuous delivery (CD) is all about delivering new code releases as fast as possible to customers. CD is a part of a greater deployment pipeline and is a successor to and also dependent on continuous integration. The continuous integration is fully responsible for running automated tests against any new code changes and verifying that those changes don’t break established features or introduce any new bugs.

Automated testing ensures quality at every stage of development by ensuring new commits do not introduce any bugs, so the software remains deployment ready at all times.

## What kinds of software tests be automated? <a href="#what-kinds-of-software-tests-be-automated" id="what-kinds-of-software-tests-be-automated"></a>

### Unit tests <a href="#unit-tests" id="unit-tests"></a>

A unit test basically has the following properties:&#x20;

* low-level, focusing on a small part of the software system
* usually written by the programmers themselves using their regular tools&#x20;
* expected to be significantly faster than other kinds of tests.

Object-oriented design tends to treat a class as a unit. But really it's a situational thing - the team decides what makes sense to be a unit for the purposes of their understanding of the system and its testing.&#x20;

Currently, in ECM there are unit tests for a specific java class in at.mic.ecm.edis. The unit tests are integrated in Jenkins build for at.mic.ecm.edis so that they are executed every 5 minutes and/or after commit with the build  [at.mic.ecm.edis](https://jenkins-miccust.msappproxy.net/view/Java%20Multibranch%20Builds/view/1\_Libraries/job/gradle-lib-multibranch-at.mic.ecm.edis/job/trunk/)​​​​​​​.

### Integration tests <a href="#integration-tests" id="integration-tests"></a>

Integration tests determine if independently developed units of software work correctly when they are connected to each other. The point of integration testing, as the name suggests, is to test **whether many separately developed modules work together as expected.**

There are (at least) two different notions about what constitutes an integration test:

* **Broad:** Where you spin up live versions of all services and run tests against them. Broad tests need substantial setup and maintenance to maintain and are often conducted in a staging environment where all systems run. Broad integration tests try to verify the correctness over how one service interprets another service’s contract like a database.&#x20;
* **Narrow:** Where you test an individual service but mocks most of its external dependencies. Narrow integration tests assume that the contract is correct and has more tests for how a single system interacts with that contract.

Currently, in ECM-EDIS there are integration tests that be executed against the database and/or integration tests for some EDIS routes to verify without a database. The DB integration tests are available in [/testing-pipelines/system-ecm/\_daily\_03-run-db-integration-tests](https://jenkins-miccust.msappproxy.net/view/Deliveries%20Pipelines/job/deliveries-pipelines/job/testing-pipelines/job/system-ecm/job/\_daily\_03-run-db-integration-tests/).

### System tests <a href="#system-tests" id="system-tests"></a>

System Testing is a level of testing that validates the complete and fully integrated software product. The purpose of a system test is to evaluate the end-to-end system specifications. In software engineering, a system test takes place after unit and integration testing. It helps to identify system errors. System Testing involves testing the software code for following:

* Testing the fully integrated applications including external peripherals in order to check how components interact with one another and with the system as a whole. This is also called End to End testing scenario.
* Verify thorough testing of every input in the application to check for desired outputs.
* Testing of the user’s experience with the application.&#x20;

In ECM there are a set of system tests to verify ECM using webservice interface. The most recent report about the executed system tests can be found in [/testing-pipelines/system-ecm/\_daily\_03-run-system-tests](https://jenkins-miccust.msappproxy.net/view/Deliveries%20Pipelines/job/deliveries-pipelines/job/testing-pipelines/job/system-ecm/job/\_daily\_03-run-system-tests/)

### Acceptance Tests <a href="#acceptance-tests" id="acceptance-tests"></a>

This testing technique is performed to determine whether or not the software system has met the requirement specifications. The main purpose of this test is to evaluate the system's compliance with the business requirements and verify if it is has met the required criteria for delivery to end-users.

Acceptance tests can come in different levels of granularity. Most of the time they will be rather high-level and test your service through the user interface. However, it's good to understand that there's technically no need to write acceptance tests at the highest level. Acceptance tests could be written at a lower level If your application design and your scenario at hand permits.

Currently, in ECM there are acceptance tests at a lower level which are intgrated in [/testing-pipelines/system-ecm/\_daily\_03-run-db-integration-tests](https://jenkins-miccust.msappproxy.net/view/Deliveries%20Pipelines/job/deliveries-pipelines/job/testing-pipelines/job/system-ecm/job/\_daily\_03-run-db-integration-tests/) (See package at.mic.edis.ecm.integration)

### Approval Tests <a href="#approval-tests" id="approval-tests"></a>

The common mechanism for Approval testing is that you run the software, gather the output and store it. The combination of (a) exactly how you set up and ran the software and (b) the stored output, forms the basis of a test case.&#x20;

Approval testing tries to solve the issue faced when you try to test a feature that has as an output something more complex than a simple number, a case where you can use assertion-based testing. Approval testing works also fine in the situation where you maintain legacy code.

In ECM there are approval tests that be executed against the database. The most recent report about the executed approval tests against the database can be found in [/testing-pipelines/system-ecm/\_daily\_03-run-db-integration-tests](https://jenkins-miccust.msappproxy.net/view/Deliveries%20Pipelines/job/deliveries-pipelines/job/testing-pipelines/job/system-ecm/job/\_daily\_03-run-db-integration-tests/).  The approval tests are integrated in Build for [at.mic.ecm.edis](https://jenkins-miccust.msappproxy.net/view/Java%20Multibranch%20Builds/view/1\_Libraries/job/gradle-lib-multibranch-at.mic.ecm.edis/job/trunk/)​​​​​​​ as well and will be executed in-memory during ECM-EDIS build.

### User Interface (GUI) tests <a href="#user-interface-gui-tests" id="user-interface-gui-tests"></a>

GUI Testing is a software testing type that checks the Graphical User Interface of the Software. The purpose of Graphical User Interface (GUI) Testing is to ensure the functionalities of software application work as per specifications by checking screens and controls like menus, buttons, icons, etc.

Currently, the UI tests for ECM are run daily with Jenkins build [/testing-pipelines/system-ecm/\_daily\_03-run-standard-ui-tests](https://jenkins-miccust.msappproxy.net/view/Deliveries%20Pipelines/job/deliveries-pipelines/job/testing-pipelines/job/system-ecm/) for system-test. The most recent report about the executed GUI tests can be found in [Standard UI Tests](https://jenkins-miccust.msappproxy.net/view/Deliveries%20Pipelines/job/deliveries-pipelines/job/testing-pipelines/job/system-ecm/job/\_daily\_03-run-standard-ui-tests/Allure\_20Report/).

Links

* [https://martinfowler.com/bliki/UnitTest.html](https://martinfowler.com/bliki/UnitTest.html)
* [https://martinfowler.com/bliki/IntegrationTest.html](https://martinfowler.com/bliki/IntegrationTest.html)
* [https://martinfowler.com/articles/practical-test-pyramid.html](https://martinfowler.com/articles/practical-test-pyramid.html)
* [https://proagile.se/blog/say-approval-testing-instead-of-golden-master](https://proagile.se/blog/say-approval-testing-instead-of-golden-master)
