## Amplify and Cognito

- The Amplify Auth category provides an interface for authenticating a user. Behind the scenes, it provides the necessary authorization to the other Amplify categories

- Configure Auth Category
1. To start provisioning auth resources in the backend, go to your project directory and execute the command:
> amplify add auth

2. To push your changes to the cloud, execute the command:
>amplify push

> amplifyconfiguration.json should be updated to reference provisioned backend auth resources.

- Install Amplify Libraries
- Add the following dependency to your app's build.gradle along with others you added above in Prerequisites and click "Sync Now" when prompted:

dependencies {
    implementation 'com.amplifyframework:aws-auth-cognito:1.24.0'
}

- Initialize Amplify Auth
Add the Auth plugin before calling Amplify.configure

// Add this line, to include the Auth plugin.
Amplify.addPlugin(new AWSCognitoAuthPlugin());
Amplify.configure(getApplicationContext());


