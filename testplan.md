# Non-Functional Test Plan

<ins>Risk Analysis</ins>

* Our app may contain unexpected bugs that we have not encountered during testing.
* Our app may slow down under heavy use or mass data storage.
* A sudden shutdown may occur due to external factors (like electrical problems).
* Because we plan to store data locally on a device, it may be a risk factor that data can be lost when the device
  malfunctions.
* Commit on GitHub may conflict with other commits from the other team members.
* If we use Google to synchronize data, this may become a weak link during peak activity hours.
* A confusing or inconvenient UI may discourage daily usage of our app.
* The version of each development environment may be different.

<ins>Performance parameters</ins>

Some things to consider when our app is in use are:

Phone speed will be a factor in our app functionality because all calculations are happening locally. Because we store
data locally, the internal storage capacity of the phone may become a factor. For some features to work the app needs to
be able to run in the background. Other features may also require the phone to produce sound, vibrations or even have a
functioning front camera.

<ins>Security vulnerabilities</ins>

Local storage also presents a risk for security. During a device loss or device data leak all personal data stored in
Relievely may be lost. Disregarding the difficulty of this task, encrypting data may solve this problem.

A remote-accessed phone may be a risk, this can be easily solved by locking the app with a separate password, but this
introduces more effort for the user. An alternative solution is disabling screen recording in our app.

If we use Google accounts to store and backup information, loss of this Google account or even loss of the Google itself
may present a risk for user data. 
