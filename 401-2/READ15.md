## Get the last known location 

- Using the Google Play services location APIs, your app can request the last known location of the user's device. In most cases, you are interested in the user's current location, which is usually equivalent to the last known location of the device.


- use the fused location provider to retrieve the device's last known location. 
- The fused location provider is one of the location APIs in Google Play services. 
- It manages the underlying location technology and provides a simple API so that you can specify requirements at a high level, like high accuracy or low power. 
- It also optimizes the device's use of battery power.

1. Set up Google Play services
- To access the fused location provider, your app's development project must include Google Play services. Download and install the Google Play services component via the SDK Manager and add the library to your project. For details, see the guide to Setting Up Google Play Services.

2. Specify app permissions
- Apps whose features use location services must request location permissions, depending on the use cases of those features.

3. Create location services client
- In your activity's onCreate() method, create an instance of the Fused Location Provider Client as the following code snippet shows.

4.  Get the last known location
1. Once you have created the Location Services client you can get the last known location of a user's device. 
- When your app is connected to these you can use the fused location provider's getLastLocation() method to retrieve the device location. - The precision of the location returned by this call is determined by the permission setting you put in your app manifest, as described in the guide on how to request location permissions.

2. To request the last known location, call the getLastLocation() method. The following code snippet illustrates the request and a simple handling of the response:


- The getLastLocation() method returns a Task that you can use to get a Location object with the latitude and longitude coordinates of a geographic location. The location object may be null in the following situations:

1. Location is turned off in the device settings. The result could be null even if the last location was previously retrieved because disabling location also clears the cache.
2. The device never recorded its location, which could be the case of a new device or a device that has been restored to factory settings.
3. Google Play services on the device has restarted, and there is no active Fused Location Provider client that has requested location after the services restarted. To avoid this situation you can create a new client and request location updates yourself. For more information, see Receiving Location Updates.


- Choose the best location estimate
The FusedLocationProviderClient provides several methods to retrieve device location information. Choose from one of the following, depending on your app's use case:

1. getLastLocation() gets a location estimate more quickly and minimizes battery usage that can be attributed to your app. However, the location information might be out of date, if no other clients have actively used location recently.
getCurrentLocation() gets a fresher, more accurate location more consistently. However, this method can cause active location computation to occur on the device

2. This is the recommended way to get a fresh location, whenever possible, and is safer than alternatives like starting and managing location updates yourself using requestLocationUpdates(). If your app calls requestLocationUpdates(), your app can sometimes consume large amounts of power if location isn't available, or if the request isn't stopped correctly after obtaining a fresh location.