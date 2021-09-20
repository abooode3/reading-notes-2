## Amplify and Kinesis 


- Goal To setup and configure your application with Amplify Analytics and record an analytics event.

- Prerequisites Install and configure Amplify CLI An Android application targeting Android API level 16 (Android 4.1) or above For a full example of creating Android project, please follow the project setup walkthrough

- Set up Analytics backend Run the following command in your project’s root folder. The CLI will prompt configuration options for the Analytics category such as Amazon Pinpoint resource name and analytics event settings.

- amplify add analytics

? Select an Analytics provider (Use arrow keys) Amazon Pinpoint ? Provide your pinpoint resource name: yourPinpointResourceName ? Apps need authorization to send analytics events. Do you want to allow guests and unauthenticated users to send analytics events? (we recommend you allow this when getting started) Yes


### amplify push

- Install Amplify Libraries Expand Gradle Scripts, open build.gradle (Module: app). You will already have configured Amplify by following the steps in the Project Setup walkthrough.


- ublic class MyAmplifyApp extends Application { @Override public void onCreate() { super.onCreate();

    try {
        // Add these lines to add the AWSCognitoAuthPlugin and AWSPinpointAnalyticsPlugin plugins
        Amplify.addPlugin(new AWSCognitoAuthPlugin());
        Amplify.addPlugin(new AWSPinpointAnalyticsPlugin(this));
        Amplify.configure(getApplicationContext());

        Log.i("MyAmplifyApp", "Initialized Amplify");
    } catch (AmplifyException error) {
        Log.e("MyAmplifyApp", "Could not initialize Amplify", error);
    }
} }