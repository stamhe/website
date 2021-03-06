---
Title: Reinstalling an Android app without losing data
Date: 2014-12-11 11:20
Modified: 2015-01-22 03:07
Author: Carey Metcalfe
Tags: android
---

When an application isn't opening (and clearing the cache doesn't help) it
sometimes helps to reinstall it. However, uninstalling then reinstalling the
app normally will delete all the data associated with it.

The way around this is to directly call the package manager from the shell and
give it the `-k` argument, which tells it to keep the data and cache directories.

Simply connect the device to a computer with [ADB][] installed and run:

```bash
adb -d shell "pm uninstall -k com.package.name"
```

Then just reinstall the app (either from an apk file or the [Play Store][]) and
the app will be back with all of its data intact.

  [ADB]: http://developer.android.com/tools/help/adb.html
  [Play Store]: https://play.google.com/store
