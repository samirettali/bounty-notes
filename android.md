# Android

* Decompile an APK, search for `*.firebaseio.com` and try to access `*.firebaseio.com/.json`, there may be a DB
* Decompile an APK and search for `s3.*`
* Grep for `android.permission.WRITE_EXTERNAL_STORAGE` in the Manifest or calls to `getExternal*`
* Grep for `application/vnd.android.package-archive`
* Search encoded string, for example `bytes[...]`
