## Finished... ##

Sorry, but I really no longer have time to maintain any of the projects here.

If you'd like to look at or work on the source, [SourceTarball.zip](http://code.google.com/p/moonblink/downloads/detail?name=SourceTarball.zip) in the Downloads section contains the latest source code.

## Pre-Requisites ##

These instructions are written for Eclipse users.  I guess you can do this without Eclipse, but I've never done that; so if you want to go that way, good luck, but you're on your own.  I strongly recommend Eclipse in any case.

To work on projects that use JavaCC, you will need the [JavaCC builders plugin](http://eclipse-javacc.sourceforge.net/).

**You must have the latest Android SDK tools.**  Run the "Android SDK and AVD Manager" from Eclipse's "Window" menu to update.  Note that this will require the corresponding version of the Android ADT plugin for Eclipse.

After updating the SDK tools, **you must restart Eclipse**, even though Eclipse doesn't require it.  Otherwise the library linkage won't work.

## Setup ##

Most of my apps pull in code from two libraries:

  * HermitLibrary is OS-independent Java code which could be used across all platforms.
  * HermitAndroid is a library of utilities specific to Android.

To work on one of the Moonblink projects, please do the following:

  * Set up a workspace for working on these projects
  * Unpack [SourceTarball.zip](http://code.google.com/p/moonblink/downloads/detail?name=SourceTarball.zip) in that workspace.
  * In Eclipse, select File -> Import -> General -> Existing projects into workspace.
  * Navigate to "HermitLibrary" and import it.
  * Same for "HermitAndroid".
  * Same for whatever app you want to work on.

If you do that right, the application should find both HermitLibrary and HermitAndroid OK.  You can check these in the project properties -- in "Java Build Path", "HermitLibrary" should be a required project, and in the "Android" preferences, "HermitAndroid" should be in the libraries list.  Then you're good to go.

**Note:** you may need to clean several times before Eclipse picks up all the class paths.  Try clean-building HermitLibrary, HermitAndroid, then the app, **separately** and in that order.

Note that the character encoding for your project must be set to Unicode, which is the java standard.  If you get errors about invalid characters, try this (thanks to R.Mayo):

> In Eclipse, open the Properties windows for HermitLibrary, select Resource, and change Text File Encoding (in the center of the window) FROM "Inherited from Container" TO "Other", and select UTF-8.