---
layout: fullpost
title: Continuous Delivery
summary: All the things I highlighted during a recent re-read of Jez Humble and Dave Farley's 'Continuous Delivery'.
published: true
---

#### CHAPTER 1 - THE PROBLEM OF DELIVERING SOFTWARE

- There should be just two human tasks involved in a software release - pick the version and environment, and press deploy.

- Deployments should be repeatabe and reliable.

- The deployment process should be used by everyone and must be the only way of getting to production.

- The deployment process should be used by everyone and must be the only way of getting to production.

- All changes must be in in version control.

- We also need an automated rollback process, if the deployment goes wrong.

- Push-button software releases

- Our aim is to find ways to reduce cycle time, to create an effective feedback loop.

- Frequent releases mean smaller deltas and easier rollback

- Building and testing the application on every check in is known as continuous integration

- If any environment configuration changes, the whole system needs to be tested.

- Defects are best detected when they are introduced, not late in the process.

- Every check in should lead to a potential release. Every change is a release candidate.

- Integration is painful so we should do it more often - as a result of every single change in the system.

- If we have sufficient tests and are running them on a production like environment, our software should always be in a releasable state.

- The purpose of a continuous integration system is to prove that the change/release candidate is not fit for production

- A deployment includes provisioning the infra, installing the correct version of the app, configuring the app including data or state.

- We should automate the bottlnecks, and automate over time.

- All aspects should be in version control, referenced by the same unique identifier that represents that build version.

- we should be able to see which builds are in which environments and which versions from version control these builds derived from.

- 'Build quality in' - Deming.

- Everyone on the delivery team is responsible for quality all of the time.

- Regular retrospectives (involving everyone) on the delivery process - and continuous improvement.

#### CHAPTER 2 - CONFIGURATION MANAGEMENT

- CM records the evolution of your systems over time.

- Everything should be reproducible and easily changeable and easily traceable back.

- No binaries in version control.

- Don't branch - commit to trunk and version control regularly - continuous integration.Find issues more quickly!

- Run a pre-commit test suite before checking in.

- Use good commit messages.

- Create a repo with approved dependencies

- No passwords in version control.

- Ping external services during deployment.

- Make environment creation a fully automated process.

- Production environments should be completely locked down.

#### CHAPTER 3 - Implementing Continuous Integration

- Goal of CI - to keep your software in a working state at all times. Software is broken until proven otherwise.

- Integration is a useful exercise, so we do it more often.

- CI is a practice not a tool - Checking in small incremental changes to mainline frequently and commiting to fixing any resulting issues immediately.

- Impossible to do CI with branches as branches are, by definition, not integrated.

- COMMIT - Compile, run unit tests, create deployable binary, run acceptance tests against binary.

- Don't check in on a broken build.

- Run commit tests locally before committing.

- To do CI effecively, everyone needs access to the whole codebase so each developer can fix any part of the code broken during the build.

- 'The only way to get excellent unit test coverage is through test driven development'

- If tests run quickly, developers will check in more frequently. Avoid slow-running tests.

- Fail builds on warnings or at least, fail it if the net result of build is more warnings, not less.

#### CHAPTER 4 - Implementing a Testing Strategy

- A test strategy tells us how we address certain risks in our product

- Limit automated acceptance testing to complete coverage of happy paths and limited coverage of the most importnt other parts.

- Testing at the right time leads to better code.

- When starting automation mid project or even post-project, begin with highest value application use cases (most common, happy paths, broad tests) then defend them with regression tests.

- Legacy systems are those without automated tests.

- Integration testing - service provider should provide replicas for other teams to use.

- Zero defect approach. James Shore.

- Testing is about establishing feedback loops that drive development, desigm and release.

###### (the following taken from Chapter 12 - Managing Data, but seems a better fit here)

- We test to assert the behaviour we desire is present. We run unit tests to protect ourselves against committing a change that breaks the app. We run acceptance tests to assert the app delivers value to users. We run capacity tests to assert that our capacity tests are satisfied. We run integration tests to assert that our application is communicating effectively with services it depends on.

- Good commit tests avoid elaborate data setup.

- We want to minimise the data specific to each test to that which it needs to prove the behaviour it is trying to assert.

- We want to avoid that our tests are reliant on complex, large data structures.

- Use the apps API to manage the data needed for your test.

- Re-use auto acceptance test as input to capacity tests.

#### CHAPTER 5 - Anatomy of the deployment pipeline

- Much of the waste in software release comes from the progress of software through testing and operations.

- We can check hashes of binaries to prove they are the same at each stage of the deployment pipeline.

- Why we only build once - more efficient, builds upon solid foundations.

- Should be able to see on a dashnoard the status of all releases.

- Best back-out strategy is to keep the previous version of your release while deploying the new version. Otherwise, redeploy the last known good version.

- Model your pipeline as a value stream. Your pipeline is your model of the process for build, deploy, test, release.

- Information radiators for your pipeline!

- The most important global metric is cycle time, but there are other diagnostics that can warn you of problems

#### CHAPTER 6 - Build and Deploy Scripting

- Developers and operations staff should decide how to automated deployments together.

- If middleware tools come with tools to configure and deploy - use them.

- If your app is tested, built and and integrated as a single piece, deploy it as a single piece.

- You can deploy on the component that it changing if you have already tested the existing combination of components, in production.

- When deploying we need to be testing at each layer post deployment, to check for presence or absence of key components.

- We need traceability between binaries and revision control

- Don't fail build on failed tests. Give it a warning colour and highlight the issues.

#### CHAPTER 7 - The Commit Stage

- Commit stage is the bouncer at the door, that does not allow unfit for prod builds to make it through the pipeline.

- In commit phase, we either create a deployable artifact or fail fast and tell team why.

- We can also run commit tests before checking, to get even earlier feedback.

- We want an aggregated report of all commit failures, but don't necessarily always want to fail the build.

- Keep scripts modular, keeping common tasks separate from frequently changing tasks.

- Avoid environment specific scripts.

- Give developers ownership.

- We can purge binaries that failed, as we are no longer interested in them.

- Keep hashes of your binaries in permanent storage so we can verify we can recreate exactly the same thing and audit back from production.

- Commit stage provides the biggest bang for our buck in the deployment pipeline!

#### CHAPTER 8 - Automated Acceptance Testing

- Acceptance tests not only help with regression but make us consider, what does success look like for each requirement?

- A DSL is a programming language targeted at solving a problem specific to a particular problem domain.

- Auto acceptance tests written with involvement of testers are better at finding defets than developer tests.

- Need to be pitched at the right level - at the leevel of behaviour and not implementaion. "If I place an order, is it accepted?"

- Auto acceptance tests differ from user acceptance tests - and should not run in an environment that includes integration to external systems.

- We can use test doubles to represent the connection external systems.

- Acceptance tests should be run against every build that passes the commit tests - tests that run later are the ones that rely more on human judgement.

- Without excellent auto acceptance test coverage, we find bugs late and/or we spend lots of time/money on manual acceptance/regression testing and or the released software is of poor quality.

- Automated acceptance tests should be created, owned and maintained by the delivery team, not a separate testing team.

- When an acceptance test breaks, the team must stop to triage and fix as soon as possible.

- Use deployment tests to show the deployment has been successful and to give us a known-good starting position.

- Automated acceptance tests will pay for itself many times over, allowing us to change large parts of our system safely.

#### CHAPTER 9 - Testing NFRs

- Difference between performance and capacity - performance is the time taken to process a single transaction, capacity is the max throughput a system can sustain while maintaining acceptable response times per transaction.

- Identify your capacity risks at the start of a project and work to avoid running in to them.

- Use production traffic to guide your tests.

- Create graphs for capacity tests that show trends over time.

- Isolate capacity test environments from other influences.

- NFRs are the equivalent of making sure bridge beams are strong enough to cope with load and weather. These are crucial to the person building the bridge but probably not foremost in the minds of the people paying for it (they want a solution to get from one side to the other).

#### CHAPTER 10 - Deploying and Releasing Applications

- Difference between deploying and releasing is the ability to roll back.

- Should always be possible to see exactly which versions of your application are in which environments, who authorized the deployment and what changes have been made to the app since it was last deployed.

- Define a release strategy to ensure a shared understanding of the release lifecycle.

- Model the release process (as a diagram)

- Pre-deployment, the environment and infra need to be put into a clean state. This shoud be fully automated.

- Promote environment and app config at same time as binaries.

- Get your deployment into prod before release! Separate deployments from release.

- Roll-backs are essential. Complicating factors are data that has been changed during the deployment and orchestrated releases of many systems.

- Firstly - ensure there is a backup of production before doing a release.

- Blue/Green - 2 x prods, deploy new version to green then gradually redirect people from blue to green (more challenging for DBs given the data migration involved). If there is only 1 prod, have two copies running on the server in isolated spaces with their own resources. OR, use staging as your second prod.

- Canary releasing - rollout new app to a subset of the production users. Rollback easy - just stop routing users to the bad version.

- Emergency fixes - do not subvert your process!! They should go through the same build/deploy/test process as all other changes. This also encourages us to keep our cycle time low. Sometimes, easier to rollback to a previous version than to try and fix.

- Allow some 'warm-up' time for new deployments.

#### CHAPTER 11 - Managing Infrastructure and Environments

- Your desired state of infra should be specified through version controlled config.

- Log all errors to a well-known location, with appropriate severity.

- If some infra config is specific to a specific app, its deployment should be tied to the app and it should not have its own lifecycle.

- Lock down prod changes to everybody, without exception.

- Should be possible to see a history of changes made to each environment including deployments.

- We need the capability to delpoy infra changes from version control.

- Be wary of expensive middleware tools that are not capable of being deployed or configured in an automated way.

- Logging is your friend.

- Avoid 'works of art'.

- We should be retriggering our pipeline every time infra changes, just like we do with app changes.

- For monitoring, we need to collect data at the levels of hardware, OS, middleware and application.

#### CHAPTER 12 - Managing Data

- Automated scripts to erase DB, create DB and load DB with data.

- Effective technique is to version your entire databases and have two scripts - one to take it forward a version and another to roll it back.

- Test data - have your tests create the data, use it, then return DB to its original state.

#### CHAPTER 13 - Managing Components and Dependencies

- How to keep your application releasable always? Hide functionality until it is ready, or make small changes each of which is releasable, or break up into components that change at different rates.

- Use configuration settings to turn on and off components.

- Shipping semi-completed functionality is a good practice because it means we are always integrating and testing the entire system, as it exists at any one time.

- Libraries - software packages our team does not control.

- Components - software packages built by us, that we are dependent on.

- Build time dependencies used at compile time, run-time dependencies used while it running, doing its normal thing.

- Splitting a large codebase into components should primarily be done to increase our efficiency as a team.

- Pipelining your components - have a single pipeline for your entire application.

- Use an integration pipeline to collate the binaries for the release then deploy them together as an integrated set, before continuing with the testing stages of the pipeline
