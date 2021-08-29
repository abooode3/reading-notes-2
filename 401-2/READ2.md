## Understand Tasks and Back Stack 

- A task: is a collection of activities that users interact with when performing a certain job.
Back button let new activity is finished and popped off the stack. The following video provides a good overview of how the back stack works.

1. When the current activity starts another, the new activity is pushed on the top of the stack and takes focus
2.  previous activity remains in the stack, but is stopped
3.  When an activity stops, the system retains the current state of its user interface
4. When the user presses the Back button, the current activity is popped from the top of the stack (the activity is destroyed) and the previous activity resumes


- what happen when click on back button ? 
### Activities in the stack are never rearranged, only pushed and popped from the stack—pushed onto the stack when started by the current activity and popped off when the user leaves it using the Back button

### If the user continues to press Back, then each activity in the stack is popped off to reveal the previous one, until the user returns to the Home screen (or to whichever activity was running when the task began). When all activities are removed from the stack, the task no longer exists.


## Managing Tasks
- the principal <activity> attributes you can use are:

1. taskAffinity
2. launchMode
3. allowTaskReparenting
4. clearTaskOnLaunch
5. alwaysRetainTaskState
6. finishOnTaskLaunch

- And the principal intent flags you can use are:

1. FLAG_ACTIVITY_NEW_TASK
2. FLAG_ACTIVITY_CLEAR_TOP
3. FLAG_ACTIVITY_SINGLE_TOP


- Defining launch modes: allow to define how a new instance of an activity is associated with the current task

1. Using the manifest file->
When you declare an activity in your manifest file, you can specify how the activity should associate with tasks when it starts.

2. Using Intent flags ->
When you call startActivity(), you can include a flag in the Intent that declares how (or whether) the new activity should associate with the current task.

## Handling affinities
- affinity indicates which task an activity prefers to belong to.
- all the activities from the same app have an affinity for each other

## Save key-value data 
- A SharedPreferences object points to a file containing key-value pairs and provides simple methods to read and write them.
- Each SharedPreferences file is managed by the framework and can be private or shared.
- You can modify the affinity for any given activity with the taskAffinity attribute of the <activity> element.

- The affinity comes into play in two circumstances:
1. When the intent that launches an activity contains the FLAG_ACTIVITY_NEW_TASK flag.
2. When an activity has its allowTaskReparenting attribute set to "true".


- You can create a new shared preference file or access an existing one by calling one of these methods:

1. getSharedPreferences() — Use this if you need multiple shared preference files identified by name, which you specify with the first parameter. You can call this from any Context in your app.

2. getPreferences() — Use this from an Activity if you need to use only one shared preference file for the activity. Because this retrieves a default shared preference file that belongs to the activity, you don't need to supply a name.