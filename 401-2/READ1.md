## Application Fundamentals 

* Android apps can be written using Kotlin, Java, and C++ languages
* Android SDK tools compile your code along with any data and resource files into an APK or an Android App Bundle.

* An Android package:
- archive file with an .apk suffix ->  contains the contents of an Android app that are required at runtime and it is the file that Android-powered devices use to install the app
- An Android App Bundle:
-  archive file with an .aab suffix, contains the contents of an Android app project including some additional metadata that is not required at runtime.


* Each Android app lives in its own security sandbox, protected by the following Android security features: 
1. The Android operating system is a multi-user Linux system in which each app is a different user.
2. By default, the system assigns each app a unique Linux user ID (The system sets permissions for all the files in an app so that only the user ID assigned to that app can access them)
3. Each process has its own virtual machine (VM), so an app's code runs in isolation from other apps.
4. every app runs in its own Linux process.

* there are ways for an app to share data with other apps and for an app to access system services:
1. It's possible to arrange for two apps to share the same Linux user ID.
>  able to access each other's files. To conserve system resources, apps with the same user ID can also arrange to run in the same Linux process and share the same VM
2. An app can request permission to access device data such as the device's location, camera, and Bluetooth connection.


* There are four different types of app components:
1. Activities
2. Services
3. Broadcast receivers
4. Content providers


- Activities: 
An activity is the entry point for interacting with the user. It represents a single screen with a user interface.

* An activity facilitates the following key interactions between system and app:
1. Keeping track of what the user currently cares about (what is on screen) to ensure that the system keeps running the process that is hosting the activity.
2. Knowing that previously used processes contain things the user may return to (stopped activities), and thus more highly prioritize keeping those processes around.
3. Helping the app handle having its process killed so the user can return to activities with their previous state restored.
4. Providing a way for apps to implement user flows between each other, and for the system to coordinate these flows. 


- Services: 
1. A service is a general-purpose entry point for keeping an app running in the background for all kinds of reasons
2.  It is a component that runs in the background to perform long-running operations or to perform work for remote processes (A service does not provide a user interface)

- Broadcast receivers:
1.  that enables the system to deliver events to the app outside of a regular user flow, allowing the app to respond to system-wide broadcast announcements.
- he system can deliver broadcasts even to apps that aren't currently running.
> A broadcast receiver is implemented as a subclass of BroadcastReceiver and each broadcast is delivered as an Intent object. For more information, see the BroadcastReceiver class.

- Content providers:
- A content provider manages a shared set of app data that you can store in the file system, in a SQLite database, on the web, or on any other persistent storage location that your app can access
-  app with the proper permissions can query the content provider, such as ContactsContract.Data

There are a few particular things this allows the system to do in managing an app:
1. Assigning a URI doesn't require that the app remain running, so URIs can persist after their owning apps have exited
2. These URIs also provide an important fine-grained security model

* A unique aspect of the Android system design is that any app can start another app’s component

Activating components:
1. Three of the four component types—activities, services, and broadcast receivers—are activated by an asynchronous message called an intent.
2.  Intents bind individual components to each other at runtime.
> An intent is created with an Intent object, which defines a message to activate either a specific component (explicit intent) or a specific type of component (implicit intent).

There are separate methods for activating each type of component:

1. You can start an activity or give it something new to do by passing an Intent to startActivity() or startActivityForResult() (when you want the activity to return a result).
2. use the JobScheduler class to schedule actions.
3. You can initiate a broadcast by passing an Intent to methods such as sendBroadcast(), sendOrderedBroadcast(), or sendStickyBroadcast().
4. You can perform a query to a content provider by calling query() on a ContentResolver.


The manifest file:
1. Identifies any user permissions the app requires, such as Internet access or read-access to the user's contacts.

2. Declares the minimum API Level required by the app, based on which APIs the app uses.
3. Declares hardware and software features used or required by the app, such as a camera, bluetooth services, or a multitouch screen.

4. Declares API libraries the app needs to be linked against (other than the Android framework APIs), such as the Google Maps library.


- Declaring components
1. In the <application> element, the android:icon attribute points to resources for an icon that identifies the app.
2. In the <activity> element, the android:name attribute specifies the fully qualified class name of the Activity subclass and the android:label attribute specifies a string to use as the user-visible label for the activity.

* You must declare all app components using the following elements:
- < activity> elements for activities.
- < service> elements for services.
- < receiver> elements for broadcast receivers.
- < provider> elements for content providers.


- Declaring component capabilities:
The system identifies the components that can respond to an intent by comparing the intent received to the intent filters provided in the manifest file of other apps on the device.

- If another app creates an intent with the ACTION_SEND action and passes it to startActivity(), the system may start your activity so the user can draft and send an email.

- Declaring app requirements
The values for minSdkVersion and targetSdkVersion are set in your app module's build.gradle file:

android {
  ...
  defaultConfig {
    ...
    minSdkVersion 26
    targetSdkVersion 29
  }
}






