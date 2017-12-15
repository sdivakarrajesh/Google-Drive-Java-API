# Uploading-Files-to-Google-drive-using-java-client-api-in-Android

To use this code

##  Get the credentials
-First go to 
[console.developers.google.com](https://console.developers.google.com)
and enable G+ api and Drive Api
-Then get the google services JSON from [here](https://developers.google.com/mobile/add?platform=android&cntapi=signin&cnturl=https:%2F%2Fdevelopers.google.com%2Fidentity%2Fsign-in%2Fandroid%2Fsign-in%3Fconfigured%3Dtrue&cntlbl=Continue%20Adding%20Sign-In) and add it to the app folder of your android project


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

Adding the library
This app uses the apache io library to copy the inputStream to a file you can download it [here](https://github.com/sdivakarrajesh/Uploading-Files-to-Google-drive-using-java-client-api-in-Android/blob/master/app/libs/commons-net-3.6.jar) and [here](https://github.com/sdivakarrajesh/Uploading-Files-to-Google-drive-using-java-client-api-in-Android/blob/master/app/libs/commons-io-2.6.jar)
Use this [link](https://stackoverflow.com/questions/16608135/android-studio-add-jar-as-library) to learn how to add external libraries to your android studio projects