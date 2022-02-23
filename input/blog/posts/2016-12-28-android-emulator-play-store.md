Title: How to install the Play Store in an API 25 emulator
Published: 2016-12-28
Category: news
---
**UPDATE 7-15-2018:**

**As of Android Studio 3.0, this procedure is no longer necessary, as there are both Nexus 5 and Nexus 5X AVD images available with Google Play already installed.**

I recently was in a situation where I needed to test a Google Maps API app on a virtual device.
When I launched the app, I got an error message about Google Play services needing to be
installed in order for the app to be usable. This was strange, I thought, because I had
intentionally downloaded the Google Play Services image instead of the plain one. However, it
seems that, even if you download the Google Play Services image, you still need to have the
Play Store installed in order to use the Maps API. Currently, the only Android emulator with
official support for the Play Store is Genymotion, which is a paid product. Instead of this,
I decided to try to manually install the Play Store from the OpenGapps "Pico"
package (http://opengapps.org/). This package contains a directory called "Core," which contains a large number of
.tar.lz archives. To extract these archives, you must use L-Zip (http://www.nongnu.org/lzip/lzip.html). However, doing this
only extracts the .lz part. In order to extract the full archive, you must use another
program that is capable of processing .tar files (e.g. [7-zip](http://www.7-zip.org/)). The archives that you need
to extract are: gmscore-X (where X is the type of image you are using), 
gsfcore-all, gsflogin-all, and vending-all. Before these archives can be pushed to the 
emulator, you must start the emulator in writable mode. To do this, open a command prompt
to the Android\sdk\tools\ directory and type
<pre><code>emulator -avd YOUR_DEVICE_NAME -writable-system -selinux permissive</code></pre>.
Once the emulator has been opened, start a new command prompt in the
Android\sdk\platform-tools\ directory and type
<pre><code>adb root
adb remount</code></pre> in order to remount the filesystem in writable mode.
You now will be able to push the previously-extracted APKs:
<pre><code>adb push PrebuiltGmsCore.apk /system/priv-app/PrebuiltGmsCore
adb push GoogleServicesFramework.apk /system/priv-app/GoogleServicesFramework
adb push GoogleLoginService.apk /system/priv-app/GoogleLoginService
adb push Phonesky.apk /system/priv-app/Phonesky
</code></pre>

Next, you must make these APKs executable:
<pre><code>adb shell
chmod 777 /system/priv-app/PrebuiltGmsCore
chmod 777 /system/priv-app/GoogleServicesFramework
chmod 777 /system/priv-app/GoogleLoginService
chmod 777 /system/priv-app/Phonesky
</code></pre>

Finally, restart the emulator:
<pre><code>adb stop
adb start
</code></pre>

If you encounter messages about Google Play Services not behaving properly (e.g. crashing), try deleting the current AVD and making a new one using the image that you just patched.

Now, you should see the Play Store icon on your dashboard.

I would like to thank the people who replied to these StackOverflow posts: http://stackoverflow.com/questions/5095234/how-to-get-root-access-on-android-emulator, http://stackoverflow.com/questions/34291902/android-studio-emulator-does-not-come-with-play-store-for-api-23
for helping me figure this out.

Comments? Did this not work? Send me a message at jtmaher2(at)gmail(dot)com, or follow me on Twitter.