
CVE-2023-34761

CVE-2023-36351
<code>An issue in Viatom Health ViHealth for Android v.2.74.58 and before allows a remote attacker to **execute arbitrary code** via the com.viatom.baselib.mvvm.webWebViewActivity component.
</code>

CVE-2023-40038

CVE-2023-40039
<code>An issue was discovered on TG852G, TG862G, and TG1672G devices. A remote attacker (in proximity to a Wi-Fi network) can derive the default WPA2-PSK value by observing a beacon frame. </code>

CVE-2023-40040


CVE-2023-42468
<code>The com.cutestudio.colordialer application through 2.1.8-2 for Android allows a remote attacker to initiate phone calls without user consent, because of improper export of the com.cutestudio.dialer.activities.DialerActivity component.
A third-party application (without any permissions) can craft an intent targeting com.cutestudio.dialer.activities.DialerActivity via the android.intent.action.CALL action in conjunction with a tel: URI, thereby placing a phone call.</code>

CVE-2023-42469
<code>The com.full.dialer.top.secure.encrypted application through 1.0.1 for Android
 enables any installed application (with no permissions) to place
 phone calls without user interaction by sending a crafted intent via the
 com.full.dialer.top.secure.encrypted.activities.DialerActivity
 component.</code>

CVE-2023-42470
<code>The Imou Life com.mm.android.smartlifeiot application through 6.8.0 for Android allows Remote Code Execution via a crafted intent to an exported component. This relates to the com.mm.android.easy4ip.MainActivity activity. JavaScript execution is enabled in the WebView, and direct web content loading occurs.</code>


CVE-2023-42471
<code>The wave.ai.browser application through 1.0.35 for Android allows a remote attacker to execute arbitrary JavaScript code via a crafted intent.
It contains a manifest entry that exports the wave.ai.browser.ui.splash.SplashScreen activity.
This activity uses a WebView component to display web content and doesn't adequately validate or sanitize the URI or any extra data passed in the intent by a third party application (with no permissions).</code>
