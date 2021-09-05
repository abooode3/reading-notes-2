
# Intro to Serverless

 What is Serverless?
- Serverless is a cloud computing execution model where the cloud provider dynamically manages the allocation and provisioning of servers.
- A serverless application runs in stateless compute containers that are event-triggered, ephemeral and fully managed by the cloud provider.

> Serverless applications are event-driven cloud-based systems where application development rely solely on a combination of third-party services, client-side logic and cloud-hosted remote procedure calls (Functions as a Service).

1. Pricing : major advantages of using Serverless is reduced cost
2. Networking: The downside is that Serverless functions are accessed only as private APIs.
3. 3rd Party Dependencies: projects have external dependencies, they rely on libraries that are not built into the language or framework you use.

### The Serverless App
A Serverless solution consists of a web server, Lambda functions (FaaS), security token service (STS), user authentication and database.

- Client Application — The UI of your application is rendered client side in Modern Frontend Javascript App which allows us to use a simple, static web server.
- Web Server — Amazon S3 provides a robust and simple web server. All of the static HTML, CSS and JS files for our application can be served from S3.
- Lambda functions (FaaS) — They are the key enablers in Serverless architecture. Some popular examples of FaaS are AWS Lambda, Google Cloud Functions and Microsoft Azure Functions. AWS Lambda is used in this framework. The application services for logging in and accessing data will be built as Lambda functions. These functions will read and write from your database and provide JSON responses.
- Security Token Service (STS) — generates temporary AWS credentials (API key and secret key) for users of the application. These temporary credentials are used by the client application to invoke the AWS API (and thus invoke Lambda).
-User Authentication — AWS Cognito is an identity service which is integrated with AWS Lambda. With Amazon Cognito, you can easily add user sign-up and sign-in to your mobile and web apps. It also has the options to authenticate users through social identity providers such as Facebook, Twitter or Amazon, with SAML identity solutions, or using your own identity system.
- Database — AWS DynamoDB provides a fully managed NoSQL database. DynamoDB is not essential for a serverless application but is used as an example here.

> Serverless architecture is certainly very exciting, but it comes with a bunch of limitations. As the validity and success of architectures depend on the business requirements and by no means solely on technology

