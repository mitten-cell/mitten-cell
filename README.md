- 👋 Hi, I’m @mitten-cell
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
mitten-cell/mitten-cell is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->Public Methods
public Task<String> getAppInstanceId ()
Retrieves the app instance id from the service, or null if FirebaseAnalytics.ConsentType.ANALYTICS_STORAGE has been set to FirebaseAnalytics.ConsentStatus.DENIED.

Returns
Task with the result of the retrieval
See Also
setConsent(Map)
public static FirebaseAnalytics getInstance (Context context)
Returns the singleton FirebaseAnalytics interface.

Parameters
context	the context used to initialize Firebase Analytics. Must not be null.
public void logEvent (String name, Bundle params)
Logs an app event. The event can have up to 25 parameters. Events with the same name must have the same parameters. Up to 500 event names are supported. Using predefined FirebaseAnalytics.Event and/or FirebaseAnalytics.Param is recommended for optimal reporting.

Parameters
name	The name of the event. Should contain 1 to 40 alphanumeric characters or underscores. The name must start with an alphabetic character. Some event names are reserved. See FirebaseAnalytics.Event for the list of reserved event names. The "firebase_", "google_" and "ga_" prefixes are reserved and should not be used. Note that event names are case-sensitive and that logging two events whose names differ only in case will result in two distinct events.
params	The map of event parameters. Passing null indicates that the event has no parameters. Parameter names can be up to 40 characters long and must start with an alphabetic character and contain only alphanumeric characters and underscores. String, long and double param types are supported. String parameter values can be up to 100 characters long. The "firebase_", "google_" and "ga_" prefixes are reserved and should not be used for parameter names.
public void resetAnalyticsData ()
Clears all analytics data for this app from the device and resets the app instance id.

public void setAnalyticsCollectionEnabled (boolean enabled)
Sets whether analytics collection is enabled for this app on this device. This setting is persisted across app sessions. By default it is enabled.

Parameters
enabled	Whether analytics collection is enabled for this app on this device.
public void setConsent (Map<FirebaseAnalytics.ConsentType, FirebaseAnalytics.ConsentStatus> consentSettings)
Sets the applicable end user consent state (e.g., for device identifiers) for this app on this device. Use the consent map to specify individual consent type values. Settings are persisted across app sessions. By default consent types are set to "granted".

Parameters
consentSettings	The map of consent types. Supported consent type keys are FirebaseAnalytics.ConsentType.AD_STORAGE and FirebaseAnalytics.ConsentType.ANALYTICS_STORAGE. Valid values are FirebaseAnalytics.ConsentStatus.GRANTED and FirebaseAnalytics.ConsentStatus.DENIED.
public void setCurrentScreen (Activity activity,String screenName,String screenClassOverride)
This method is deprecated.
To log screen view events, call mFirebaseAnalytics.logEvent(FirebaseAnalytics.Event.SCREEN_VIEW, params) instead.

Sets the current screen name, which specifies the current visual context in your app. This helps identify the areas in your app where users spend their time and how they interact with your app.

Note that screen reporting is enabled automatically and records the class name of the current Activity for you without requiring you to call this function. The class name can optionally be overridden by calling this function in the onResume callback of your Activity and specifying the screenClassOverride parameter.

If your app does not use a distinct Activity for each screen, you should call this function and specify a distinct screenName each time a new screen is presented to the user.

The name and classOverride remain in effect until the current Activity changes or a new call to setCurrentScreen is made.

This method must be called from the app's main thread.

Parameters
activity	The activity to which the screen name and class name apply.
screenName	The name of the current screen. Set to null to clear the current screen name.
screenClassOverride	The name of the screen class. By default this is the class name of the current Activity. Set to null to revert to the default class name.
public void setDefaultEventParameters (Bundle parameters)
Adds parameters that will be set on every event logged from the SDK, including automatic ones. The values passed in the parameters bundle will be added to the map of default event parameters. These parameters persist across app runs. They are of lower precedence than event parameters, so if an event parameter and a parameter set using this API have the same name, the value of the event parameter will be used. The same limitations on event parameters apply to default event parameters.

Parameters
parameters	Parameters to be added to the map of parameters added to every event. They will be added to the map of default event parameters, replacing any existing parameter with the same name. Valid parameter values are String, long, and double. Setting a key's value to null will clear that parameter. Passing in a null bundle will clear all parameters.
public void setSessionTimeoutDuration (long milliseconds)
Sets the duration of inactivity that terminates the current session. The default value is 1800000 (30 minutes).

Parameters
milliseconds	Session timeout duration in milliseconds
public void setUserId (String id)
Sets the user ID property. This feature must be used in accordance with Google's Privacy Policy.

Parameters
id	The user ID to ascribe to the user of this app on this device, which must be non-empty and no more than 256 characters long. Setting the ID to null removes the user ID.
public void setUserProperty (String name, String value)
Sets a user property to a given value. Up to 25 user property names are supported. Once set, user property values persist throughout the app lifecycle and across sessions.

Parameters
name	The name of the user property to set. Should contain 1 to 24 alphanumeric characters or underscores and must start with an alphabetic character. The "firebase_", "google_" and "ga_" prefixes are reserved and should not be used for user property names.
value	The value of the user property. Values can be up to 36 characters long. Setting the value to null removes the user property.


