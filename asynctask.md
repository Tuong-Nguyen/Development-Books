AsyncTask allows task to run on **background thread **and report the progress and result on **UI thread.**

### **Scenario:** 

we would like to run long UI handler without freezing the application.

### **Implementation:**

##### Create a Task

AsyncTask&lt;Params, Progress, Result&gt;

* Params: type of task parmaters
* Progress: type of progress values
* Result: type of result value

Override methods:

* protected void **onPreExecute**\(\): UI Thread - before the task runs
* protected Result **doInBackground**\(Params... params\): background thread - task
* protected void **onPostExecute**\(Result result\): UI Thread - after task completes
* protected void **onProgressUpdate**\(Progress... values\): UI Thread - progress of task
* protected void **onCancelled**\(Result result\): UI Thread - task is cancelled

##### Calling the task

```java
Task task = new Task();
task.execute(param);
```

### Considerations:

Task class is often implemented as** Inner class** of an **Activity **so that it has a reference to parent instance to update the UI in its onPostExecute method. However, _activity has a life cycle controlled by OS_. If the activity instance is destroyed then onPostExecute accesses to an destroyed instance and causes exception.

##### Solution: 

1. AsyncTask and ensure that the task always completes before activity is destroyed.
2. Loader which is life cycle awareness.



