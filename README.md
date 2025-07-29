# AndroidAPS with autoISF
* For documentation about AndroidAPS without autoISF, check the wiki: https://androidaps.readthedocs.io
* Everyone who’s been looping with AndroidAPS needs to fill out the form after 3 days of looping  https://docs.google.com/forms/d/14KcMjlINPMJHVt28MDRupa4sz4DDIooI4SrW0P3HSN8/viewform?c=0&w=1

## What is autoISF?
AutoISF adds more power to the algorithm used in AndroidAPS by adjusting the insulin sensitivity based on different scenarios (e.g. high BG,
accelerating/decelerating BG, BG plateau). autoISF has many different settings to fine-tune these adjustments.
However, it is important to start with well-tested basal rate and settings for insulin sensitivity and carb ratios.

## Where to find documentation about autoISF
* Please visit ga-zelle’s repository [GitHub - ga-zelle/autoISF](https://github.com/ga-zelle/autoISF/tree/A3.3.3.a%2Baisf3.1.0).
  The [**Quick Guide (bzw. Kurzanleitung)**](https://github.com/ga-zelle/autoISF/blob/A3.3.3.a%2Baisf3.1.0/autoISF3.1.0_Quick_Guide.pdf) provides an overview of autoISF and its features


## Why do I get AutoISF here and not at ga-zelle's Repo?
* The vast majority of the AutoISF design and development effort was done by [ga-zelle](https://github.com/ga-zelle) with support from
  [swissalpine](https://github.com/swissalpine), [claudi](https://github.com/lutzlukesch),
  [BerNie](https://github.com/bherpichb), [mountrcg](https://github.com/mountrcg),
  [Bjr](https://github.com/blaqone), [Gohtraw](https://github.com/Gohtraw),
  [Koelewij](https://github.com/koelewij) and [myself](https://github.com/T-o-b-i-a-s).
* This repository here was created to provide a stable version of AndroidAPS with the current autoISF extensions
  already integrated to simplify the build process.
* This branch https://github.com/T-o-b-i-a-s/AndroidAPS/tree/3.3.3.a+aisf3.1.0 uses
  AndroidAPS 3.3.3-dev-a from the official [Nightscout AndroidAPS]
  (https://github.com/nightscout/AndroidAPS)
  repo as a base and adds autoISF 3.1.0 to it.

## What's new in AutoISF Version 3.1.0 when compared to AutoISF 3.0.3
* Provides autoISF as an APS Algorithm plugin (was integrated into SMB in the past)
* Calibrating and smoothing for Libre sensors without xDrip+
* Logfiles are stored in hourly slices in Documents/aapsLogs to make them accessible to tools on the phone
* Improved support for 1-minute glucose values from Freestyle Libre 3
* Improved output of autoISF results in autoISF Tab

## Why was autoISF not added to the current AndroidAPS "master" version 3.3.2.0?
* With AndroidAPS 3.3, autoISF was introduced as a plugin, but can only be enabled in dev mode
* Fixes to support Omnipod DASH on Android 16 were integrated from the dev branch
* As a preparation for the upcoming release of AndroidAPS 3.3.3.

## How to build this branch in Android Studio
1. Get the latest version of Android Studio
2. Close any currently open projects in Android Studio
3. Create a new project by using the "Get from VCS" button to tell it to retrieve the source from a remote version control system
4. Use the url of this repository as a source (https://github.com/T-o-b-i-a-s/AndroidAPS.git). Do NOT append any branch name
   or version number or other path, **just use the URL as listed above**!
5. Now wait until Android has completed any initialization activities. As always deny any requests to upgrade Gradle. A "Gradle sync" might however be necessary.
6. Android Studio now shows the name of the current branch on the upper left within the title bar.

* Usually this will be `master`, which contains an out-dated version of AndroidAPS, do **not** use the `master` branch
* If it is not already selected, switch to the branch you want to build by clicking on the branch name,
  choosing "show more" under "Remote branches" and look for the name of
  the branch with an "origin/" prefix: e.g. `origin/3.3.3.a+aisf3.1.0`. Left-click that name and
  select "Checkout". 
7. The system will now create a local branch with the same name as the remote branch and switch to that branch, which is indicated by the name of
   the branch being shown in the upper right corner
8. You can now build the APK with Build -> Generate signed Bundle / APK
9. If you get an error about an incompatible JVM or Java Version, read the troubleshooting section within the official
   [AndroidAPS documentation](https://androidaps.readthedocs.io/en/latest/GettingHelp/TroubleshootingAndroidStudio.html#incompatible-gradle-jvm)
10. In case of any error messages during the build, try to first run a "Clean build" by selecting
   Build -> Clean to remove any remnants from previous builds and then start the APK build again.
1If you experience recurring problems with building the APK, as a last resort consider to
    delete your current Android Studio completely, reinstall the most recent version and clone
    this repo into a new directory on your computer (different than the one you have used before).

## What can I do if the build does not work?
* Follow the instructions exactly as described. Carefully re-read all previous and the failing step and try to start from scratch.
* Make sure you used "https://github.com/T-o-b-i-a-s/AndroidAPS.git" as the URL to "Get from VCS" and none including the branch or version name
* If you have problems understanding English and need a translation, consider using an automatic translation tool such as
  https://www.deepl.com where you have to copy and paste the english text to get it translated or use
  [Google Translate](https://github-com.translate.goog/T-o-b-i-a-s/AndroidAPS?_x_tr_sl=en&_x_tr_tl=de&_x_tr_hl=de&_x_tr_pto=wapp)
  to automatically translate the whole page (target language is set to German in this example, but can be changed at the top).

General remark:
If you have been working with older AndroidAPS versions (2.x, 3.0, 3.1, 3.2) before and this is the first time you build a 3.3 version,
please first build and run the regular AndroidAPS 3.3.x version from
https://github.com/nightscout/AndroidAPS and double-check that this works fine.
Only then upgrade to the version including autoISF.

For questions or feedback, please contact us at https://de.loopercommunity.org/t/woher-wie-autoisf/
