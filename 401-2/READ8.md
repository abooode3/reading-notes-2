# Intro to Serverless
What is Serverless?

- Serverless is a cloud computing execution model where the cloud provider dynamically manages the allocation and provisioning of servers.
- A serverless application runs in stateless compute containers that are event-triggered, ephemeral and fully managed by the cloud provider.

# AWS Amplify
1. AWS Amplify is a set of tools and services that can be used together or on their own, to help front-end web and mobile developers build scalable full stack applications, powered by AWS. With Amplify, you can configure app backends and connect your app in minutes, deploy static web apps in a few clicks, and easily manage app content outside the AWS console.

2. Amplify supports popular web frameworks including JavaScript, React, Angular, Vue, Next.js, and mobile platforms including Android, iOS, React Native, Ionic, Flutter. Get to market faster with AWS Amplify.


## Add relationships between types
###  @connection 
- directive enables to specify relationships between @model types.
-  supports one-to-one, one-to-many, and many-to-one relationships.
- Relationships between types are specified by annotating fields on an @model object type with the @connection directive.
- The fields argument can be provided and indicates which fields can be queried by to get connected objects.
- The keyName argument can optionally be used to specify the name of secondary index (an index that was set up using @key
- When specifying a keyName, the fields argument should be provided to indicate which field(s) will be used to get connected objects.


## Generates
- In order to keep connection queries fast and efficient, the GraphQL transform manages global secondary indexes (GSIs) on the generated tables on your behalf when using @connection
