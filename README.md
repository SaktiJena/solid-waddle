# solid-waddle
Serverless Architecture: Five Design Patterns

Consultant Ken Fromm recently wrote on A Cloud Guru's Medium blog that serverless architecture allows developers to focus on managing what their applications and systems need to do, rather than the physical capabilities, limits, and complexity of their backend infrastructure, in order to summarise the current maturity of serverless technologies. As a result, in a serverless environment, a job or task serves as the unit of scale.

According to Fromm, "the task processing effectively becomes container processing with the containers built up and removed on a task per task basis." This indicates that tasks typically have an asynchronous, stateless, and transient nature.

According to Bonner at APIdays, the cloud teams view serverless computing as consisting of four key tenets:

1. Simple but usable primitives (i.e. small, useable building blocks).
2. Scales with usage (servers are autoscaled on the user’s behalf).
3. Pay-only usage (customers only pay for the time using services).
4. Built-in availability and fault tolerance (i.e. NoOps).

While startups have typically been "all in" from the start, established businesses with legacy systems have frequently followed a different path over the past year or so. They have built new applications, added analytics, and started to migrate some of their legacy applications before concentrating on migrating mission-critical apps to cloud.

According to Stanski, businesses of all sizes tended to be "all in" this year from the get-go. They would start the process of migrating the current legacy stacks while simultaneously developing new apps using their cloud hosting services.

While new applications may be developed using serverless architecture, for the most part, businesses were using hybrid approaches, in which new features were developed in a serverless environment and then woven in and out of existing application hosting architecture environments. This was the trend Bonner described in the adoption of serverless.

According to Bonner, "This is how we are seeing a lot of customers start off": a company might already have a workflow in place for managing image data. It might then add an image recognition feature that runs in a serverless environment, and the catalogued results would then be piped back into the legacy workflow, which might be located in a user's cloud-hosted environment.

The five serverless patterns for use cases that Bonner defined were:

1. Event-driven data processing.
2. Web applications.
3. Mobile and Internet-of-Things applications.
4. Application ecosystems.
5. Event workflows.

Use case #1: Event-driven Data Processing
One of the most common applications for serverless environments is to trigger actions after an event occurs. Bonner gave the example of an image object being added to an Amazon S3 bucket. That may trigger a lambda function, for example, to run a compression task so that the image is re-archived into S3 in a standard size format.

This style of use case also fits well with the hybrid trend, where serverless is being leveraged to perform specific functions within a wider hosted environment.

#2: Serverless Web Applications
In a serverless web app, there may be a combination of running processes that determine contextual and personal elements of the user to serve content and functionality that meets the user’s needs. In this use case, for example, static content might be stored in S3 to display when the application is opened in the browser.

At the same time, processing is initiated through the application’s API gateway to run Lambda functions that determine the application user’s context. The static content is then enhanced with more dynamic content that is generated through the lambda functions and stored as dynamic data in DynamoDB.

#3: Mobile and Internet of Things Applications
Similar to the web apps use case, mobile and IoT applications built in a serverless environment are looking to decide on what content to offer the user based on their context. Serverless authentication elements are used to ensure the user — whether that be a human or a machine — is authorized appropriately to access information or functionality. Lambdas then carry out functionality and interact with data in a DynamoDB to meet the user’s needs.


#4: Serverless Application Ecosystems
In an app ecosystem, applications or workflows are created in a serverless environment and draw on a combination of AWS functionalities and products alongside third party provider APIs.

Bonner gave an example of someone telling an Amazon Echo that they were giving a presentation, that voice data then triggering a lambda function to pass that message on to a remote team via the Slack API. Polling within the serverless environment then identifies when the team has responded and messages the Echo with the feedback.

#5: Event Workflow
Decision trees can be created in Step Functions that then align with Lambdas and AWS products to carry out workflow branched actions (although it was confusing that Amazon Web Services were highlighting Step Functions in Australia given it is not available there as yet).

For example, using a pub/sub messaging model, it is possible to visualize and have all functions and distributed components drawn through a state machine. Users can map the customer onboarding process, entry into CRM, shopping cart ordering and order fulfillment through Step Functions and lambdas and AWS tools are automatically added to ensure the workflow can be completed.

So while Fromm talks about serverless being predominantly asynchronous, stateless and ephemeral, once getting into more complex workflows and applications, some capability to persist state and make synchronous calls comes into play.

Step Functions provides state machines so that Lambda functions can have some degree of transient state available for business processes where serverless applications may need to marry synchronous and asynchronous call chains.

But power users of serverless like Ben Kehoe from iRobots believes the current pricing structure of Step Functions is too prohibitive to use it in production in serverless environments. In addition, the default throttling limits suggest that the intended use does not tend to cover scaled but transient event scheduling.

“I’m hopeful that State as-a-Service is a paradigm that can be made to work for low-level, transient state needed by FaaS in serverless architectures, whether it’s through Step Functions or another service,” wrote Kehoe late last year after Step Functions was first announced.

Authentication Choices
Within the serverless environment, it is also possible to choose a user authentication and identity management workflow best suited to the serverless design pattern and use case being implemented. Authentication methods may change depending on whether a number of users from the one organization need access with varying permission roles, whether users are predominantly customers, or whether partners have some access.
