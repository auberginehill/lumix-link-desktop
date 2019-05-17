<!-- Visual Studio Code: For a more comfortable reading experience, use the key combination Ctrl + Shift + V
     Visual Studio Code: To crop the tailing end space characters out, please use the key combination Ctrl + A Ctrl + K Ctrl + X (Formerly Ctrl + Shift + X)
     Visual Studio Code: To improve the formatting of HTML code, press Shift + Alt + F and the selected area will be reformatted in a html file.
     Visual Studio Code shortcuts: http://code.visualstudio.com/docs/customization/keybindings (or https://aka.ms/vscodekeybindings)
     Visual Studio Code shortcut PDF (Windows): https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf


  _____                                  _        _    _ _______ __  __ _        _____
 |  __ \                                (_)      | |  | |__   __|  \/  | |      |_   _|                                /\
 | |__) |_ _ _ __   __ _ ___  ___  _ __  _  ___  | |__| |  | |  | \  / | |        | |  _ __ ___   __ _  __ _  ___     /  \   _ __  _ __
 |  ___/ _` | '_ \ / _` / __|/ _ \| '_ \| |/ __| |  __  |  | |  | |\/| | |        | | | '_ ` _ \ / _` |/ _` |/ _ \   / /\ \ | '_ \| '_ \
 | |  | (_| | | | | (_| \__ \ (_) | | | | | (__  | |  | |  | |  | |  | | |____   _| |_| | | | | | (_| | (_| |  __/  / ____ \| |_) | |_) |
 |_|   \__,_|_| |_|\__,_|___/\___/|_| |_|_|\___| |_|  |_|  |_|  |_|  |_|______| |_____|_| |_| |_|\__,_|\__, |\___| /_/    \_\ .__/| .__/
                                                                                                        __/ |               | |   | |
                                                                                                       |___/                |_|   |_|
                                                                                                                                                     -->


# Unofficial HTML version of the Panasonic Image App application #

This is an unofficial and platform agnostic counterpart of the official [Panasonic](https://av.jpn.support.panasonic.com/support/global/cs/soft/image_app/) [Image App](https://play.google.com/store/apps/details?id=com.panasonic.avc.cng.imageapp&hl=en_GB) [mobile app](https://itunes.apple.com/us/app/panasonic-image-app/id590212732), which is partially similar to the older [Lumix Link](https://av.jpn.support.panasonic.com/support/global/cs/dsc/lumixlink/android/index.html) app. With this application you can remotely control your Lumix camera, take pictures, record video, adjust capture settings and so on.



## Usage Instructions ##

Basically, the usage instructions can be found at this [Personal View forum thread](http://www.personal-view.com/talks/discussion/6703/control-your-gh3-from-a-web-browser-now-with-video-/p1).

#### Tutorial <small>(basic usage without streaming the Live View to the connected device)</small>

1.  Press Menu button on the camera
2.  Go to the Setup menu
3.  Navigate to WiFi
4.  Select WiFi Function
5.  Select New Connection
6.  Select Remote Shooting & View
7.  Camera screen will now be showing the Wifi glowing beacon thing
8.  Choose the SSID ID it is showing on the camera (could be GX80-blah blah) to connect your phone or laptop to
9.  Camera will show message saying 'If you have not launched the smartphone application...' message
10. Load the HTML-page <code>Control.html</code> into the browser of your phone or laptop
11. Select 'Handshake 1'
12. The browser will display 'ok,GX80-xxxxx,remote,encrypted' on the bottom of the page (the xxxxxx will be your specific GX80 ID)
13. Select 'Connect (Start OTA Session)'
14. The browser will now display 'OK' on the bottom of the page and the camera will display 'Under Remote Control'
15. Wait until you see the live view image on the camera LCD

Credit: [BTM_Pix](https://www.eoshd.com/comments/topic/24995-would-you-perhaps-be-interested-in-a-different-gx8085-colour-profile/page/4/#comments)

#### Deploy Cinelike D on Panasonic Lumix LX10 / LX15 <sup>[1]</sup>

1. 	After the previous 15 steps in "Tutorial", set the camera to manual mode (M), and confirm that some appropriate camera settings, such as Shutter Speed or ISO, may be set with the <code>Control.html</code> page.
2. 	Switch the camera to movie/video mode.
3. 	Select Photo Style: <code>cinelike_d [submit]</code> on the <code>Control.html</code> page.
4. 	The response on the bottom of the <code>Control.html</code> page should be 'ok' and the camera should NOT now be displaying the Photo Style you had selected previously (i.e. Standard, Vivid etc.) in top left corner of the screen of the camera.
5. 	Cinelike D is now active on the camera (if indeed the Photo Style indicator seems to be blank). <sup>[2]</sup>
6. 	If you go into the menu on the camera and select Photo Style, you will see that it is blank and you can't navigate to other Photo Styles such as Standard etc.
7. 	You may want to save the no-name (Cinelike D) profile as a custom Photo Style by pressing "<code>Disp.</code>" or by saving all settings to C1, C2 or C3 custom profile bank.
8. 	To restore the original built-in video photo styles select Photo Style: <code>Standard [submit]</code> whilst in movie/video mode.

Credit: [Jon Pais](https://jonpais.wordpress.com/2017/05/)

| _______ |                                                    |
|:-------:|----------------------------------------------------|
| [1]     | May require extra/additional/different steps.      |
| [2]     | If the response is "ok", but the Photo Style indicator doesn't vanish, the Cinelike D is not deployed, but it might be deployable by using a different procedure or different steps. |



## Screenshot ##
<img class="screenshot" title="screenshot" alt="screenshot" height="100%" width="100%" src="https://raw.githubusercontent.com/auberginehill/panasonic-html-image-app/master/Panasonic-HTML-Image-App.png">



## Supported Camera Models ##

The basic parts of this application should work with all Lumix cameras that can be used with the mobile app.

However, as the cameras have different features, this application might or might not support all of them. Also, since it seems that each camera model has its own initial UPnP "Handshake" routine, some cameras might not pair at all by using the provided Handshake strings.

Furthermore, after a successful pairing (please see the Tutorial), the HTML-page <code>requests.html</code> lists all the settings on one page including settings that are not settable in each and every camera mode. For instance the focusing options "<code>mf_asst_on</code>", "<code>mf_asst_off</code>" and "<code>AF override in MF</code>" at Focus (MF) might only work as intended when Focus Mode is set to MF. Similarly, "<code>AF/AE Lock On</code>" and "<code>AF/AE Lock Off</code>" seem to require that one of the AF-modes is active on the camera.



## Origin of This Application ##

This is a "fork" of a "[fork](https://github.com/peci1/lumix-link-desktop)" of the application published on http://www.personal-view.com/talks/discussion/6703/control-your-gh3-from-a-web-browser-now-with-video-/p1 , so the credit for the initial work on reverse-engeneering the communication protocol goes to **lenuisible**.



## License ##

The license of the original application is unclear. It seems that it was given to the public without any restrictions.

Changes since version 2.0.0 (the first version of [the previous fork](https://github.com/peci1/lumix-link-desktop)) are covered by the 3-clause BSD license.



## www ##

|  Home:  | [Unofficial HTML version of the Panasonic Image App application](https://github.com/auberginehill/panasonic-html-image-app)                                 |
|:-------:|-------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Fork:  | [Unofficial desktop Lumix Link application](https://github.com/peci1/lumix-link-desktop) (the previous fork)                                                |
|  Other: | [LMaster](https://github.com/Rambalac/GMaster)                                                                                                              |
| Camera: | [Panasonic Lumix LX10/LX15 settings](https://gist.github.com/auberginehill/132104749d2da304a48ebccb90571dfd)                                                |
| Credit: | lenuisible [Control your GH3 from a Web Browser](http://www.personal-view.com/talks/discussion/6703/control-your-gh3-from-a-web-browser-now-with-video-/p1) |
