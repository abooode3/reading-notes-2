## Espresso 
- Use Espresso to write concise, beautiful, and reliable Android UI tests.

### Record an Espresso test
Espresso tests consist of two primary components:
1.  UI interactions: include tap and type actions that a person may use to interact with app
2. assertions on View elements : verify the existence or contents of visual elements on the screen.

### Synchronization capabilities
Each time your test invokes onView(), Espresso waits to perform the corresponding UI action or assertion until the following synchronization conditions are met:

1. The message queue is empty.
2. There are no instances of AsyncTask currently executing a task.
3. All developer-defined idling resources are idle.

### Packages
- espresso-core - Contains core and basic View matchers, actions, and assertions. See Basics and Recipes.
- espresso-web - Contains resources for WebView support.
- espresso-idling-resource - Espresso's mechanism for synchronization with background jobs.
- espresso-contrib - External contributions that contain DatePicker, RecyclerView and Drawer actions, accessibility checks, and CountingIdlingResource.
- espresso-intents - Extension to validate and stub intents for hermetic testing.
- espresso-remote - Location of Espresso's multi-process functionality.

### Add assertions to verify UI elements

- Assertions verify the existence or contents of a View element through three main types:
1. text is: Checks the text content of the selected View element
2. exists: Checks that the View element is present in the current View hierarchy visible on the screen
3. does not exist: Checks that the View element is not present in the current View hierarchy

