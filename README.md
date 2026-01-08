# Security Advisories (CVE)

## Table of Contents
1. [RCE / Command Injection](#remote-code-execution)
2. [Default Credentials / Cryptographic Attacks](#default-credentials--cryptographic-attacks)
3. [Privilege Escalation](#privilege-escalation)
4. [Broken Access Control](#broken-access-control)
5. [XSS and Arbitrary JavaScript Code Execution](#xss-and-arbitrary-javascript-code-execution)
6. [Information Disclosure](#information-disclosure)
7. [Misc](#miscellaneous)



|                |                |                |                |                |
|----------------|----------------|----------------|----------------|----------------|
| **Not Disclosed:** | CVE-2025-68707 | CVE-2025-68708 | CVE-2025-68709 | CVE-2025-68710 |
| CVE-2025-68711 | CVE-2025-68712 | CVE-2025-68713 | CVE-2025-68720 |  |
|  |   |   |   |  |



## Remote Code Execution

- **CVE-2025-68706**
  - **Description**: A stack-based buffer overflow exists in the GoAhead-Webs HTTP daemon on KuWFi 4G LTE AC900 devices with firmware 1.0.13. The /goform/formMultiApnSetting handler uses sprintf() to copy the  user-supplied pincode parameter into a fixed 132-byte stack buffer with no bounds checks. This allows an attacker to corrupt adjacent stack memory, crash the web server, and (under certain conditions) may enable arbitrary code execution.
    
- **CVE-2025-43989**
  - **Description**: The /goform/formJsonAjaxReq POST endpoint of Shenzhen Tuoshi NR500-EA RG500UEAABxCOMSLICv3.4.2731.16.43 devices mishandles the set_timesetting action with the ntpserver0 parameter, which is used in a system command.
By setting a username=admin cookie (bypassing normal session checks), an unauthenticated attacker can use that parameter to execute arbitrary OS commands.

- **CVE-2025-43984**
  - **Description**: An issue was discovered on KuWFi GC111 devices (Hardware Version: CPE-LM321_V3.2, Software Version: GC111-GL-LM321_V3.0_20191211). They are vulnerable to unauthenticated /goform/goform_set_cmd_process requests. A crafted POST request, using the SSID parameter, allows remote attackers to execute arbitrary OS commands with root privileges.

- **CVE-2025-43979**
  - **Description**: An issue was discovered on FIRSTNUM JC21A-04 devices through 2.01ME/FN that allows authenticated attackers to execute arbitrary OS system commands with root privileges via crafted payloads to the xml_action.cgi?method= endpoint.

- **CVE-2025-43978**
  - **Description**: Jointelli 5G CPE 21H01 firmware JY_21H01_A3_v1.36 devices allow (blind) OS command injection. Multiple endpoints are vulnerable, including /ubus/?flag=set_WPS_pin and /ubus/?flag=netAppStar1 and /ubus/?flag=set_wifi_cfgs. This allows an authenticated attacker to execute arbitrary OS commands with root privileges via crafted inputs to the SSID, WPS, Traceroute, and Ping fields.

- **CVE-2024-53945**
  - **Description**: The KuWFi 4G AC900 LTE router 1.0.13 is vulnerable to command injection on the HTTP API endpoints /goform/formMultiApnSetting and /goform/atCmd. An authenticated attacker can execute arbitrary OS commands with root privileges via shell metacharacters in parameters such as pincode and cmds. Exploitation can lead to full system compromise, including enabling remote access (e.g., enabling telnet).

- **CVE-2024-53944**
  - **Description**: An issue was discovered on Tuoshi/Dionlink LT15D 4G Wi-Fi devices through M7628NNxlSPv2xUI_v1.0.1802.10.08_P4 and LT21B devices through M7628xUSAxUIv2_v1.0.1481.15.02_P0.
A unauthenticated remote attacker with network access can exploit a command injection vulnerability. The /goform/formJsonAjaxReq endpoint fails to sanitize shell metacharacters sent via JSON parameters, thus allowing attackers to execute arbitrary OS commands with root privileges.

- **CVE-2024-53942**
  - **Description**:  An issue was discovered on NRadio N8-180 NROS-1.9.2.n3.c5 devices. The /cgi-bin/luci/nradio/basic/radio endpoint is vulnerable to command injection via the 2.4 GHz and 5 GHz name parameters, allowing a remote attacker to execute arbitrary OS commands on the device (with root-level permissions) via crafted input.

- **CVE-2024-53940**
  - **Description**: An issue was discovered in Victure RX1800 WiFi 6 Router (software EN_V1.0.0_r12_110933, hardware 1.0) devices. Certain /cgi-bin/luci/admin endpoints are vulnerable to command injection. Attackers can exploit this by sending crafted payloads through parameters intended for the ping utility, enabling arbitrary command execution with root-level permissions on the device.

- **CVE-2024-53939**
  - **Description**: An issue was discovered in Victure RX1800 WiFi 6 Router (software EN_V1.0.0_r12_110933, hardware 1.0) devices. The /cgi-bin/luci/admin/opsw/Dual_freq_un_apple endpoint is vulnerable to command injection through the 2.4 GHz and 5 GHz name parameters, allowing an attacker to execute arbitrary commands on the device (with root-level permissions) via crafted input.

- **CVE-2024-45242**
  - **Description**: EnGenius ENH1350EXT A8J-ENH1350EXT devices before firmware version v3.9.4.1_c1.9.51, allow (blind) OS Command Injection via shell metacharacters to the Ping or Speed Test utility. During the time of initial setup, the device creates an open unsecured network whose admin panel is configured with the default credentials of admin/admin. An unauthorized attacker in proximity to the Wi-Fi network can exploit this window of time to execute arbitrary OS commands with root-level permissions.

- **CVE-2024-36061**
  - **Description**: EnGenius EWS356-FIT devices through 1.1.30 allow (blind) OS command injection. This allows an attacker to execute arbitrary OS commands via shell metacharacters to the Ping and Speed Test utilities.

- **CVE-2024-36060**
  - **Description**: EnGenius EnStation5-AC A8J-ENS500AC 1.0.0 devices allow (blind) OS command injection via shell metacharacters in the Ping and Speed Test parameters.

- **CVE-2024-31976**
  - **Description**: EnGenius EWS356-FIT 1.1.30 and earlier devices allow a remote attacker to execute arbitrary OS commands via the Controller connectivity parameter.

- **CVE-2024-31977**
  - **Description**: Adtran 834-5 11.1.0.101-202106231430 devices allow OS Command Injection via shell metacharacters to the Ping or Traceroute utility.

## Default Credentials / Cryptographic Attacks

- **CVE-2025-68718**
  - **Description**:  KAYSUS KS-WR1200 routers with firmware 107 expose SSH and TELNET services on the LAN interface with hardcoded root credentials (root:12345678). The administrator cannot disable these services or change the hardcoded password. (Changing the management GUI password does not affect SSH/TELNET authentication.) Any LAN-adjacent attacker can trivially log in with root privileges.
    
- **CVE-2025-68716**
  - **Description**: KAYSUS KS-WR3600 routers with firmware 1.0.5.9.1 enable the SSH service enabled by default on the LAN interface. The root account is configured with no password, and administrators cannot disable SSH or enforce authentication via the CLI or web GUI. This allows any LAN-adjacent attacker to trivially gain root shell access and execute arbitrary commands with full privileges.

- **CVE-2025-68714**
  - **Description**: An issue was discovered in Panda Wireless PWRU0 devices with firmware 2.2.9 that enables TELNET by default and exposes it over the WAN interface with default credentials (admin/admin), granting remote attackers the ability to run  arbitrary commands OS commands.

- **CVE-2025-43986**
  - **Description**: An issue was discovered on KuWFi GC111 GC111-GL-LM321_V3.0_20191211 devices. The TELNET service is enabled by default and exposed over the WAN interface without authentication.

- **CVE-2025-43982**
  - **Description**: Shenzhen Tuoshi NR500-EA RG500UEAABxCOMSLICv3.4.2731.16.43 devices enable the SSH service by default. There is a hidden hard-coded root account that cannot be disabled in the GUI.

- **CVE-2025-43980**
  - **Description**: An issue was discovered on FIRSTNUM JC21A-04 devices through 2.01ME/FN. They enable the SSH service by default with the credentialsn of root/admin. The GUI doesn't offer a way to disable the account.
 
- **CVE-2024-53941**
  - **Description**: An issue was discovered in Victure RX1800 WiFi 6 Router (software EN_V1.0.0_r12_110933, hardware 1.0) devices. 
A remote attacker (in proximity to a Wi-Fi network) can derive the default Wi-Fi PSK value via the last 4 octets of the BSSID.

- **CVE-2024-53938**
  - **Description**: An issue was discovered in Victure RX1800 WiFi 6 Router (software EN_V1.0.0_r12_110933, hardware 1.0) devices. The TELNET service is enabled by default and exposed over the LAN. The root account is accessible without a password, allowing attackers to achieve full control over the router remotely without any authentication.

- **CVE-2024-53937**
  - **Description**: An issue was discovered on Victure RX1800 WiFi 6 Router (software EN_V1.0.0_r12_110933, hardware 1.0) devices. The TELNET service is enabled by default with admin/admin as default credentials and is exposed over the LAN. The allows attackers to execute arbitrary commands with root-level permissions. Device setup does not require
this password to be changed during setup in order to utilize the device. (However, the TELNET password is dictated by the current GUI password.)

- **CVE-2024-39345**
  - **Description**: AdTran 834-5 HDC17600021F1 (SmartOS 11.1.0.101-202106231430) devices enable the SSH service by default and have a hidden, undocumented, hard-coded support account whose password is based on the devices MAC address. All of the devices internet interfaces share a similar MAC address that only varies in their final octet. This allows network-adjacent attackers to derive the support user's SSH password by decrementing the final octet of the connected gateway address or via the BSSID. An attacker can then execute arbitrary OS commands with root-level privileges.
  
- **CVE-2024-31970**
  - **Description**: AdTran SRG 834-5 HDC17600021F1 devices (with SmartOS 11.1.0.101-202106231430) have SSH enabled by default, accessible both over the LAN and the Internet. During a window of time when the device is being set up, it uses a default username and password combination of admin/admin with root-level privileges. An attacker can exploit this window to gain unauthorized root access by either modifying the existing admin account or creating a new account with equivalent privileges. This vulnerability allows attackers to execute arbitrary commands.
  
- **CVE-2024-28093**
  - **Description**: The TELNET service of AdTran NetVanta 3120 18.01.01.00.E devices is enabled by default, and has default credentials for a root-level account.
  
- **CVE-2024-25731**
  - **Description**: The Elink Smart eSmartCam (com.cn.dq.ipc) application 2.1.5 for Android contains hardcoded AES encryption keys that can be extracted from a binary file. Thus, encryption can be defeated by an attacker who can observe packet data (e.g., over Wi-Fi).
  
- **CVE-2024-25730**
  - **Description**: Hitron CODA-4582 and CODA-4589 devices have default PSKs that are generated from 5-digit hex values concatenated with a "Hitron" substring, resulting in insufficient entropy (only about one million possibilities).
  
- **CVE-2024-25729**
  - **Description**: Arris SBG6580 devices have predictable default WPA2 security passwords that could lead to unauthorized remote access.
  
- **CVE-2024-23726**
  - **Description**: Ubee DDW365 XCNDDW365 devices have predictable default WPA2 PSKs that could lead to unauthorized remote access. A remote attacker (in proximity to a Wi-Fi network) can derive the default WPA2-PSK value by observing a beacon frame. A PSK is generated by using the first six characters of the SSID and the last six of the BSSID, decrementing the last digit.
  
- **CVE-2023-47352**
  - **Description**: Technicolor TC8715D devices have predictable default WPA2 security passwords. An attacker who scans for SSID and BSSID values may be able to predict these passwords.
  
- **CVE-2023-46919**
  - **Description**: Phlox com.phlox.simpleserver (aka Simple HTTP Server) 1.8 and com.phlox.simpleserver.plus (aka Simple HTTP Server PLUS) 1.8.1-plus have a hardcoded aKySWb2jjrr4dzkYXczKRt7K (AES) encryption key. An attacker with physical access to the application's source code or binary can extract this key & use it decrypt the TLS secret. 
  
- **CVE-2023-46918**
  - **Description**: Phlox com.phlox.simpleserver.plus (aka Simple HTTP Server PLUS) 1.8.1-plus has an Android manifest file that contains an entry with the android:allowBackup attribute set to true. This could be leveraged by an attacker with physical access to the device.
  
- **CVE-2023-40039**
  - **Description**: An issue was discovered on ARRIS TG852G, TG862G, and TG1672G devices. A remote attacker (in proximity to a Wi-Fi network) can derive the default WPA2-PSK value by observing a beacon frame.
  
- **CVE-2023-40038**
  - **Description**: Arris DG860A and DG1670A devices have predictable default WPA2 PSKs that could lead to unauthorized remote access. A remote attacker (in proximity to a Wi-Fi network) can derive the default WPA2-PSK value by observing a beacon frame. WIFI PSK's are generated by using the 1st 6 characters of the SSID + the last 6 of the BSSID, decrementing the last digit.


## Privilege Escalation

- **CVE-2025-43977**
  - **Description**: The com.skt.prod.dialer application through 12.5.0 for Android enables any installed application (with no permissions) to place phone calls without user interaction by sending a crafted intent via the com.skt.prod.dialer.activities.outgoingcall.OutgoingCallInternalBroadcaster component.

- **CVE-2025-43976**
  - **Description**: The com.enflick.android.tn2ndLine application through 24.17.1.0 for Android enables any installed application (with no permissions) to
 place phone calls without user interaction by sending a crafted intent via the com.enflick.android.TextNow.activities.DialerActivity component.

- **CVE-2024-53936**
  - **Description**: The com.asianmobile.callcolor (aka Color Phone Call Screen App) application through 24 for Android enables any application (with no permissions) to place phone calls without user interaction by sending a crafted intent via the com.asianmobile.callcolor.ui.component.call.CallActivity component.

- **CVE-2024-53935**
  - **Description**: The com.callos14.callscreen.colorphone (aka iCall OS17 - Color Phone Flash) application through 4.3 for Android enables any application (with no permissions) to place phone calls without user interaction by sending a crafted intent via the com.callos14.callscreen.colorphone.DialerActivity component.

- **CVE-2024-53934**
  - **Description**: The com.windymob.callscreen.ringtone.callcolor.colorphone (aka Color Phone Call Screen Themes) application through 1.1.2 for Android enables any application (with no permissions) to place phone calls without user interaction by sending a crafted intent via the com.frovis.androidbase.call.DialerActivity component.

- **CVE-2024-53933**
  - **Description**: The com.callerscreen.colorphone.themes.callflash (aka Color Call Theme & Call Screen) application through 1.0.7 for Android enables any application (with no permissions) to place phone calls without user interaction by sending a crafted intent via the com.android.call.color.app.activities.DialerActivity component.

- **CVE-2024-53932**
  - **Description**: The com.remi.colorphone.callscreen.calltheme.callerscreen (aka Color Phone: Call Screen Theme) application through 21.1.9 for Android enables any application (with no permissions) to place phone calls without user interaction by sending a crafted intent via the com.remi.colorphone.callscreen.calltheme.callerscreen.dialer.DialerActivity component.

- **CVE-2024-53931**
  - **Description**: The com.glitter.caller.screen (aka iCaller, Caller Theme & Dialer) application through 1.1 for Android enables any application (with no permissions) to place phone calls without user interaction by sending a crafted intent via the com.glitter.caller.screen.DialerActivity component.

- **CVE-2024-37575**
  - **Description**: The Mister org.mistergroup.shouldianswer application 1.4.264 for Android enables any installed application (with no permissions) to place phone calls without user interaction by sending a crafted intent via the org.mistergroup.shouldianswer.ui.default_dialer.DefaultDialerActivity component.
    
- **CVE-2024-37574**
  - **Description**: The GriceMobile com.grice.call application 4.5.2 for Android enables any installed application (with no permissions) to place phone call  without user interaction by sending a crafted intent via the com.iui.mobile.presentation.MobileActivity.

- **CVE-2024-37573**
  - **Description**: The Talkatone com.talkatone.android application 8.4.6 for Android enables any installed application (with no permissions) to place phone calls without user interaction by sending a crafted intent via the  
  com.talkatone.vedroid.ui.launcher.OutgoingCallInterceptor component.

- **CVE-2024-36437**
  - **Description**: The com.enflick.android.TextNow (aka TextNow: Call + Text Unlimited) application 24.17.0.2 for Android enables any installed application (with no permissions) to place phone calls without user interaction by sending a crafted intent via the com.enflick.android.TextNow.activities.DialerActivity component.

- **CVE-2024-36064**
  - **Description**: The NLL com.nll.cb (aka ACR Phone) application through 0.330-playStore-NoAccessibility-arm8 for Android allows any installed application (with no permissions) to place phone calls without user interaction by sending a crafted intent via the com.nll.cb.dialer.dialer.DialerActivity component.

- **CVE-2024-36063**
  - **Description**: The Goodwy com.goodwy.dialer (aka Right Dialer) application through 5.1.0 for Android enables any application (with no permissions) to place phone calls without user interaction by sending a crafted intent via the com.goodwy.dialer.activities.DialerActivity component.

- **CVE-2024-36062** 
  - **Description**: The com.callassistant.android (aka AI Call Assistant & Screener) application 1.174 for Android enables any installed application (with no permissions) to place phone calls without user interaction bysending a crafted intent via thecom.callassistant.android.ui.call.incall.InCallActivity component.

    
- **CVE-2023-49003**
  - **Description**: An issue in simplemobiletools Simple Dialer 5.18.1 allows an attacker to bypass intended access restrictions via interaction with com.simplemobiletools.dialer.activities.DialerActivity.
  
- **CVE-2023-49002**
  - **Description**: An issue in Xenom Technologies (sinous) Phone Dialer-voice Call Dialer v.1.2.5 allows an attacker to bypass intended access restrictions via interaction with com.funprime.calldialer.ui.activities.OutgoingActivity.
  
- **CVE-2023-47889**
  - **Description**: The Android application BINHDRM26 com.bdrm.superreboot 1.0.3, exposes several critical actions through its exported broadcast receivers. These exposed actions can allow any app on the device to send unauthorized broadcasts, leading to unintended consequences. The vulnerability is particularly concerning because these actions include powering off, system reboot & entering recovery mode.
  
- **CVE-2023-47355**
  - **Description**: The com.eypcnnapps.quickreboot (aka Eyuep Can Yilmaz {ROOT] Quick Reboot) application 1.0.8 for Android has exposed broadcast receivers for PowerOff, Reboot, and Recovery (e.g., com.eypcnnapps.quickreboot.widget.PowerOff) that are susceptible to unauthorized broadcasts because of missing input validation.
  
- **CVE-2023-47354**
  - **Description**: An issue in the PowerOffWidgetReceiver function of Super Reboot (Root) Recovery v1.0.3 allows attackers to arbitrarily reset or power off the device via a crafted intent.
  
- **CVE-2023-47353**
  - **Description**: An issue in the com.oneed.dvr.service.DownloadFirmwareService component of IMOU GO v1.0.11 allows attackers to force the download of arbitrary files.
  
- **CVE-2023-42469**
  - **Description**: The com.full.dialer.top.secure.encrypted application through 1.0.1 for Android enables any installed application (with no permissions) to place phone calls without user interaction by sending a crafted intent via the com.full.dialer.top.secure.encrypted.activities.DialerActivity component.
  
- **CVE-2023-42468**
  - **Description**: The com.cutestudio.colordialer application through 2.1.8-2 for Android allows a remote attacker to initiate phone calls without user consent, because of improper export of the com.cutestudio.dialer.activities.DialerActivity component. A third-party application (without any permissions) can craft an intent targeting com.cutestudio.dialer.activities.DialerActivity via the android.intent.action.CALL action in conjunction with a tel: URI, thereby placing a phone call.

## Broken Access Control

- **CVE-2025-68719**
  - **Description**: KAYSUS KS-WR3600 routers with firmware 1.0.5.9.1 mishandle configuration management. Once any user is logged in and maintains an active session, an attacker can directly query the backup endpoint and download a full configuration archive. This archive contains sensitive files such as /etc/shadow, enabling credential recovery and potential full compromise of the device.
    
- **CVE-2025-68717**
  - **Description**: KAYSUS KS-WR3600 routers with firmware 1.0.5.9.1 allow authentication bypass during session validation. If any user is logged in, endpoints such as /cgi-bin/system-tool accept unauthenticated requests with empty or invalid session values. This design flaw lets attackers piggyback on another user's active session to retrieve sensitive configuration data or execute privileged actions without authentication.

- **CVE-2025-68715**
  - **Description**: An issue was discovered in Panda Wireless PWRU0 devices with firmware 2.2.9 that exposes multiple HTTP endpoints (/goform/setWan, /goform/setLan, /goform/wirelessBasic) that do not enforce authentication. A remote unauthenticated attacker can modify WAN, LAN, and wireless settings directly, leading to privilege escalation and denial of service.

- **CVE-2025-43988**
  - **Description**: KuWFi 5G01-X55 FL2020_V0.0.12 devices expose an unauthenticated API endpoint (ajax_get.cgi), allowing remote attackers to retrieve sensitive configuration data, including admin credentials.

- **CVE-2025-43985**
  - **Description**: An issue was discovered on KuWFi GC111 devices (Hardware Version: CPE-LM321_V3.2, Software Version: GC111-GL-LM321_V3.0_20191211). They contain a critical vulnerability in /goform/goform_get_cmd_process and /goform/goform_set_cmd_process that allows remote unauthenticated attackers to view sensitive information such as admin credentials.

- **CVE-2025-43983**
  - **Description**: KuWFi CPF908-CP5 WEB5.0_LCD_20210125 devices have multiple unauthenticated access control vulnerabilities within goform/goform_set_cmd_process and goform/goform_get_cmd_process. These allow an unauthenticated attacker to retrieve sensitive information (including the device admin username and password), modify critical device settings, and send arbitrary SMS messages.

## XSS and Arbitrary JavaScript Code Execution

- **CVE-2024-53943**
  - **Description**: An issue was discovered in NRadio N8-180 NROS-1.9.2.n3.c5 devices. The /cgi-bin/luci/nradio/basic/radio endpoint is vulnerable to XSS via the 2.4 GHz and 5 GHz name parameters, allowing an attacker to execute JavaScript within the context of the current user by injecting JavaScript into the SSID field. If an administrator logs into the device, the injected script runs in their browser, executing the malicious payload.

- **CVE-2024-46966**
  - **Description**: The Ikhgur mn.ikhgur.khotoch (aka Video Downloader Pro & Browser) application through 1.0.42 for Android allows an attacker to execute arbitrary JavaScript code via the mn.ikhgur.khotoch.MainActivity component.

- **CVE-2024-46965**
  - **Description**: The DS allvideo.downloader.browser (aka Fast Video Downloader: Browser) application through 1.6-RC1 for Android allows an attacker to execute arbitrary JavaScript code via the allvideo.downloader.browser.DefaultBrowserActivity component.

- **CVE-2024-46964**
  - **Description**: The com.video.downloader.all (aka All Video Downloader) application through 11.28 for Android allows an attacker to execute arbitrary JavaScript code via the com.video.downloader.all.StartActivity component.

- **CVE-2024-46963**
  - **Description**: The com.superfast.video.downloader (aka Super Unlimited Video Downloader - All in One) application through 5.2.0 for Android allows an attacker to execute arbitrary JavaScript code via the com.bluesky.browser.ui.BrowserMainActivity component.

- **CVE-2024-46962**
  - **Description**: The SYQ com.downloader.video.fast (aka Master Video Downloader) application through 2.0 for Android allows an attacker to execute arbitrary JavaScript code via the com.downloader.video.fast.SpeedMainAct component.

- **CVE-2024-46961**
  - **Description**: The Inshot com.downloader.privatebrowser (aka Video Downloader - XDownloader) application through 1.3.5 for Android allows an attacker to execute arbitrary JavaScript code via the com.downloader.privatebrowser.activity.PrivateMainActivity component.

- **CVE-2024-46960**
  - **Description**: The ASD com.rocks.video.downloader (aka HD Video Downloader All Format) application through 7.0.129 for Android allows an attacker to execute arbitrary JavaScript code via the com.rocks.video.downloader.MainBrowserActivity component.


- **CVE-2024-42041**
  - **Description**: The com.videodownload.browser.videodownloader (aka AppTool-Browser-Video All Video Downloader) application 20-30.05.24 for Android allows an attacker to execute arbitrary JavaScript code via the acr.browser.lightning.DefaultBrowserActivity component.

- **CVE-2024-31975**
  - **Description**: EnGenius EWS356-Fit devices through 1.1.30 allow a remote attacker to conduct stored XSS attacks via the Wi-Fi SSID parameters. JavaScript embedded into a vulnerable field is executed when the user clicks the SSID field's corresponding EDIT button.

- **CVE-2024-31973**
  - **Description**: Hitron CODA-4582 2AHKM-CODA4589 7.2.4.5.1b8 devices allow a remote attacker within Wi-Fi proximity to conduct stored XSS attacks via the 'Network Name (SSID)' input fields to the /index.html#wireless_basic page.

- **CVE-2024-31972**
  - **Description**: EnGenius ESR580 A8J-EMR5000 devices allow a remote attacker to conduct stored XSS attacks that could lead to arbitrary JavaScript code execution (under the context of the user's session) via the Wi-Fi SSID input fields. Web scripts embedded into the vulnerable fields this way are executed immediately when a user logs into the admin page. This affects /admin/wifi/wlan1 and /admin/wifi/wlan_guest.
     
- **CVE-2024-31971**
  - **Description**: Multiple stored cross-site scripting (XSS) vulnerabilities on AdTran NetVanta 3120 18.01.01.00.E devices allow remote attackers to inject arbitrary JavaScript, as demonstrated by: /mainPassword.html, /processIdentity.html,/public.html, /dhcp.html, /private.html,/hostname.html, /connectivity.html, /NetworkMonitor.html, /trafficMonitoringConfig.html, & /wizardMain.html.
  
- **CVE-2024-28092**
  - **Description**: UBEE DDW365 XCNDDW365 8.14.3105 software on hardware 3.13.1 allows a remote attacker within Wi-Fi proximity to conduct stored XSS attacks via RgFirewallEL.asp, RgDdns.asp, RgTime.asp, RgDiagnostics.asp, or RgParentalBasic.asp parameters.
  
- **CVE-2024-28091**
  - **Description**: Technicolor TC8715D TC8715D-01.EF.04.38.00-180405-S-FF9-D RSE-TC8717T devices allow a remote attacker within Wi-Fi proximity to conduct stored XSS attacks via User Defined Service in managed_services_add.asp (the victim must click an X for a deletion).
  
- **CVE-2024-28090**
  - **Description**: Technicolor TC8715D TC8715D-01.EF.04.38.00-180405-S-FF9-D RSE-TC8717T devices allow a remote attacker within Wi-Fi proximity to conduct stored XSS attacks via User name in dyn_dns.asp.
  
- **CVE-2024-28089**
  - **Description**: Hitron CODA-4582 2AHKM-CODA4589 7.2.4.5.1b8 devices allow a remote attacker within Wi-Fi proximity (who has access to the router admin panel) to conduct a DOM-based stored XSS attack that can fetch remote resources. The payload is executed at index.html#advanced_location (aka the Device Location page). This can cause a denial of service or lead to information disclosure.
  
- **CVE-2024-31974**
  - **Description**: The com.solarized.firedown (aka Solarized FireDown Browser & Downloader) application 1.0.76 for Android allows a remote attacker to execute arbitrary JavaScript code via a crafted intent. com.solarized.firedown.IntentActivity uses a WebView component to display web content and doesn't adequately sanitize the URI or any extra data passed in the intent by any installed application (with no permissions).
  
- **CVE-2024-23729**
  - **Description**: The ColorOS Internet Browser com.heytap.browser application 45.10.3.4.1 for Android allows a remote attacker to execute arbitrary JavaScript code via the com.android.browser.RealBrowserActivity component.
  
- **CVE-2024-23727**
  - **Description**: The YI Smart Kami Vision com.kamivision.yismart application through1.0.0_20231219 for Android allows a remote attacker to execute arbitrary JavaScript code via an implicit intent to the com.ants360.yicamera.activity.WebViewActivity component.
  
- **CVE-2023-47883**
  - **Description**: The com.altamirano.fabricio.tvbrowser TV browser application through 4.5.1 for Android is vulnerable to JavaScript code execution via an explicit intent due to an exposed MainActivity.
  
- **CVE-2023-47882**
  - **Description**: The Kami Vision YI IoT com.yunyi.smartcamera application through 4.1.9_20231127 for Android allows a remote attacker to execute arbitrary JavaScript code via an implicit intent to the com.ants360.yicamera.activity.WebViewActivity component.
  
- **CVE-2023-43481**
  - **Description**: An issue in Shenzhen TCL Browser TV Web BrowseHere (aka com.tcl.browser) 6.65.022_dab24cc6_231221_gp allows a remote attacker to execute arbitrary JavaScript code via the com.tcl.browser.portal.browse.activity.BrowsePageActivity component.
  
- **CVE-2023-43955**
  - **Description**: The com.phlox.tvwebbrowser TV Bro application through 2.0.0 for Android mishandles external intents through WebView. This allows attackers to execute arbitrary code, create arbitrary files & perform arbitrary downloads via JavaScript that uses takeBlobDownloadData.
  
- **CVE-2023-42471**
  - **Description**: The wave.ai.browser application through 1.0.35 for Android allows a remote attacker to execute arbitrary JavaScript code via a crafted intent. It contains a manifest entry that exports the wave.ai.browser.ui.splash.SplashScreen activity. This activity uses a WebView component to display web content and doesn't adequately validate or sanitize the URI or any extra data passed in the intent by a third-party application (with no permissions).
  
- **CVE-2023-42470**
  - **Description**: The Imou Life com.mm.android.smartlifeiot application through 6.8.0 for Android allows Remote Code Execution via a crafted intent to an exported component. This relates to the com.mm.android.easy4ip.MainActivity activity. JavaScript execution is enabled in the WebView, and direct web content loading occurs.
  
- **CVE-2023-36351**
  - **Description**: An issue in Viatom Health ViHealth for Android v.2.74.58 and before allows a remote attacker to execute arbitrary code via the com.viatom.baselib.mvvm.webWebViewActivity component.

## Information Disclosure

- **CVE-2023-46447**
  - **Description**: The POPS! Rebel application 5.0 for Android, in POPS! Rebel Bluetooth Glucose Monitoring System, sends unencrypted glucose measurements over BLE.

## Miscellaneous
- **CVE-2023-34761**
  - **Description**: An unauthenticated attacker within BLE proximity can remotely connect to a 7-Eleven LED Message Cup, Hello Cup 1.3.1 for Android, and bypass the application's client-side chat censor filter.

- **CVE-2024-53946**
  - **Description**: The KuWFi 4G LTE AC900 router 1.0.13 is vulnerable to Cross-Site Request Forgery (CSRF) on its web management interface. This vulnerability allows an attacker to trick an authenticated admin user into performing unauthorized actions, such as exploiting a command injection vulnerability in /goform/formMultiApnSetting. Successful exploitation can also lead to unauthorized configuration changes.

