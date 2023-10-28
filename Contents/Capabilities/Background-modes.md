# Music playback
Keep music playing in the background. 
**Note**: For some reasons, this capability can sometimes keep the app running in the background *forever*

# Location update
CLLocationManager observing location changes. This can keep the app running in a long time

# Background fetches
The system decides when to perform the background fetch tasks at a suitable point when user is not using the app in foreground.
Using **BGAppRefreshAppRequest** to schedule for frequent update when backgrounds the app. 
This give about **30 secs** of runtime for the app to run in the background

# Background pushes
Silent push to wake app for a short time to perform needed data updates. 
**Note**: Be aware of background push rate, ideally >15min per push

# Background Processing
Similar to background fetch, but this gives app minutes to process long operations using BGAppRefreshAppRequest
