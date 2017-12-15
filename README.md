# Uploading-Files-to-Google-drive-using-java-client-api-in-Android

To use this code

##  Get the credentials
First go to 
{console.developers.google.com}(https://console.developers.google.com)
and get enable G+ api and Drive Api
Then get the google services JSON and add it to the app folder of your android project


##  Adding the permissions 
Be sure that you have added the following permissions in the android Manifest
 
	
	<uses-permission android:name="android.permission.GET_ACCOUNTS" />
    <uses-permission android:name="android.permission.READ_PROFILE" />
    <uses-permission android:name="android.permission.READ_CONTACTS" />
    <uses-permission android:name="android.permission.INTERNET" />
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
	

	
##  Adding the dependencies
Be sure that you have added the following dependencies in the Project level gradle build file

	classpath 'com.google.gms:google-services:3.1.0'		
 
Add the following dependencies in the App level gradle build file
	
	
	Android{
	...
	configurations.all {
			resolutionStrategy.force 'com.google.code.findbugs:jsr305:1.3.9'
		}
	...
	}		
	
	
	
	
then add
	
	
	
	compile 'com.google.android.gms:play-services-auth:11.6.2'
		compile('com.google.apis:google-api-services-drive:v3-rev90-1.23.0') {
			exclude group: 'org.apache.httpcomponents'
		}
		compile 'com.google.android.gms:play-services-drive:11.6.2'
		compile 'com.google.android.gms:play-services-auth:11.6.2'
		compile 'pub.devrel:easypermissions:0.3.0'
		compile 'com.google.oauth-client:google-oauth-client-jetty:1.23.0'
		compile('com.google.api-client:google-api-client-android:1.23.0') {
			exclude group: 'org.apache.httpcomponents'
		}
		implementation files('libs/commons-io-2.6.jar')
		implementation files('libs/commons-net-3.6.jar')
	
	
	
Below everything else add
	
	
	apply plugin: 'com.google.gms.google-services'
