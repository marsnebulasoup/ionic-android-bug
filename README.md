# ionic-android-bug
Repo of an Ionic app that fails building with an `:app:processDebugMainManifest` error.

See [this post](https://forum.ionicframework.com/t/unable-to-run-ionic-app-after-updating-capacitor-from-v2-to-v3-getting-a-processdebugmainmanifest-error/210935?u=marsnebulasoup)


**AndroidManifest.xml**
```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="io.ionic.starter">

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/AppTheme">

        <activity
            android:configChanges="orientation|keyboardHidden|keyboard|screenSize|locale|smallestScreenSize|screenLayout|uiMode"
            android:name="io.ionic.starter.MainActivity"
            android:label="@string/title_activity_main"
            android:theme="@style/AppTheme.NoActionBarLaunch"
            android:launchMode="singleTask">

            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>

        </activity>

        <provider
            android:name="androidx.core.content.FileProvider"
            android:authorities="${applicationId}.fileprovider"
            android:exported="false"
            android:grantUriPermissions="true">
            <meta-data
                android:name="android.support.FILE_PROVIDER_PATHS"
                android:resource="@xml/file_paths"></meta-data>
        </provider>
    </application>

    <!-- Permissions -->

    <uses-permission android:name="android.permission.INTERNET" />
</manifest>
```


**Full console output (verbose)**
```
Windows PowerShell
Copyright (C) Microsoft Corporation. All rights reserved.

Try the new cross-platform PowerShell https://aka.ms/pscore6

PS C:\Users\Me\Desktop\ionictest\ionic-android-bug> ionic cap sync
> vue-cli-service.cmd build

-  Building for production...(node:10788) ExperimentalWarning: Conditional exports is an experimental feature. This feature could change at any time
-  Building for production...(node:5656) ExperimentalWarning: Conditional exports is an experimental feature. This feature could change at any time
(node:5656) ExperimentalWarning: Package name self resolution is an experimental feature. This feature could change at any time
/  Building for production...(node:16828) ExperimentalWarning: Conditional exports is an experimental feature. This feature could change at any time
-  Building for production...(node:10788) ExperimentalWarning: Package name self resolution is an experimental feature. This feature could change at any time
|  Building for production...

 WARNING  Compiled with 1 warning                                                                                                                                                        4:54:55 PM
 warning 

entrypoint size limit: The following entrypoint(s) combined asset size exceeds the recommended limit (244 KiB). This can impact web performance.
Entrypoints:
  app (270 KiB)
      css/chunk-vendors.190e707f.css
      js/chunk-vendors.1d6b5269.js
      css/app.e32995c9.css
      js/app.ce460447.js


  File                                     Size                                                                       Gzipped  

  dist\js\chunk-vendors.1d6b5269.js        233.52 KiB                                                                 78.09 KiB
  dist\js\chunk-2d2297f7.78980670.js       101.07 KiB                                                                 26.96 KiB
  dist\js\polyfills-core-js.12be3461.js    91.91 KiB                                                                  30.28 KiB
  dist\js\chunk-5a8ac886.1c1bcfb0.js       62.67 KiB                                                                  8.02 KiB 
  dist\js\chunk-2d0a463b.580f9170.js       51.52 KiB                                                                  5.87 KiB 
  dist\js\chunk-53b1137a.8efb31cd.js       45.45 KiB                                                                  10.38 KiB
  dist\js\chunk-21a76241.9a71d653.js       44.48 KiB                                                                  10.96 KiB
  dist\js\chunk-1c4705f4.6dbe2887.js       38.09 KiB                                                                  7.06 KiB 
  dist\js\chunk-462c869e.0ea6ae2c.js       29.38 KiB                                                                  5.51 KiB 
  dist\js\chunk-d8413eac.9e3a3351.js       28.88 KiB                                                                  6.12 KiB 
  dist\js\chunk-25d83ca8.89659437.js       25.65 KiB                                                                  5.31 KiB 
  dist\js\chunk-a9395c36.8777d2b5.js       25.39 KiB                                                                  4.54 KiB 
  dist\js\chunk-426f2f16.9f46eefa.js       25.11 KiB                                                                  4.76 KiB 
  dist\js\chunk-5ff96a24.bc2c1407.js       23.22 KiB                                                                  4.34 KiB 
  dist\js\chunk-097e0872.3522b5ab.js       22.88 KiB                                                                  5.32 KiB 
  dist\js\chunk-3ed29de3.9e68e146.js       22.84 KiB                                                                  4.05 KiB 
  dist\js\chunk-02c995b5.c8dee7ab.js       21.98 KiB                                                                  3.84 KiB 
  dist\js\chunk-54bbd082.aa2ffdeb.js       21.02 KiB                                                                  4.72 KiB 
  dist\js\chunk-1dbc15a2.8c41fb29.js       19.66 KiB                                                                  2.34 KiB 
  dist\js\polyfills-dom.662760da.js        18.44 KiB                                                                  5.61 KiB 
  dist\js\chunk-1bff95de.c7f1bfb8.js       16.78 KiB                                                                  4.37 KiB 
  dist\js\chunk-37f2300e.cc3c45b7.js       16.37 KiB                                                                  3.58 KiB 
  dist\js\chunk-7548ca2d.f50c2a89.js       16.10 KiB                                                                  3.45 KiB 
  dist\js\chunk-41c0f7a4.5f0941d1.js       15.84 KiB                                                                  3.62 KiB 
  dist\js\chunk-79f1dac7.4481f814.js       15.66 KiB                                                                  4.16 KiB 
  dist\js\chunk-4739acd0.12a964e2.js       15.23 KiB                                                                  4.68 KiB 
  dist\js\chunk-858cd918.54b9acef.js       14.95 KiB                                                                  4.65 KiB 
  dist\js\chunk-eaa2b130.700c0fb3.js       14.67 KiB                                                                  2.91 KiB 
  dist\js\chunk-69eb8776.8f434896.js       14.42 KiB                                                                  2.82 KiB 
  dist\js\chunk-e5275ddc.a29be33a.js       12.19 KiB                                                                  3.48 KiB
  dist\js\chunk-0e93a01c.b0a5975b.js       12.01 KiB                                                                  3.03 KiB
  dist\js\app.ce460447.js                  11.91 KiB                                                                  4.04 KiB
  dist\js\chunk-2d0da04a.620f425b.js       11.71 KiB                                                                  1.75 KiB
  dist\js\chunk-6d375f34.8b250ad4.js       9.96 KiB                                                                   2.52 KiB
  dist\js\chunk-09162720.102e7a40.js       9.35 KiB                                                                   2.39 KiB
  dist\js\chunk-09155df3.e3ac211b.js       9.27 KiB                                                                   1.63 KiB
  dist\js\chunk-2d0d43da.c6672c38.js       8.84 KiB                                                                   3.11 KiB
  dist\js\chunk-2d217e6a.9d5e5387.js       8.72 KiB                                                                   3.48 KiB
  dist\js\chunk-d0e8aa0a.ef2f5d14.js       7.58 KiB                                                                   2.53 KiB
  dist\js\chunk-8bb7f81e.4465b78a.js       7.32 KiB                                                                   2.04 KiB
  dist\js\chunk-2d21da73.56e20878.js       6.72 KiB                                                                   1.76 KiB
  dist\js\chunk-2d213189.2b11f265.js       6.70 KiB                                                                   1.55 KiB
  dist\js\chunk-47245a33.b9e6a322.js       6.33 KiB                                                                   1.96 KiB
  dist\js\chunk-2d237b00.037b5772.js       5.53 KiB                                                                   2.36 KiB
  dist\js\chunk-2d0b9280.58416f48.js       5.43 KiB                                                                   2.10 KiB
  dist\js\chunk-59d4c87c.9a2960ba.js       4.81 KiB                                                                   1.30 KiB
  dist\js\chunk-2d0d5c33.d98bbfcf.js       3.92 KiB                                                                   1.65 KiB
  dist\js\chunk-2d218068.115cead1.js       3.53 KiB                                                                   1.17 KiB
  dist\js\chunk-26af9b0f.908002a9.js       2.22 KiB                                                                   0.86 KiB
  dist\js\chunk-374b839a.68a7c833.js       2.22 KiB                                                                   0.87 KiB
  dist\js\chunk-420adeb3.5b70ee52.js       2.22 KiB                                                                   0.87 KiB
  dist\js\chunk-2d0baac9.ecbd8a2b.js       2.17 KiB                                                                   0.96 KiB
  dist\js\chunk-2d0e5812.bc3079e1.js       1.87 KiB                                                                   0.76 KiB
  dist\js\chunk-2d0c073f.017f6960.js       1.77 KiB                                                                   0.72 KiB
  dist\js\chunk-2d2376e6.a05b70ee.js       1.71 KiB                                                                   0.69 KiB
  dist\js\chunk-30dd9750.6b7d6eb0.js       1.43 KiB                                                                   0.70 KiB
  dist\js\chunk-2d0b33e3.2e69defc.js       0.91 KiB                                                                   0.47 KiB
  dist\js\chunk-2d0c9758.62f099a9.js       0.75 KiB                                                                   0.49 KiB
  dist\js\chunk-2d0b9074.cf6d8bbf.js       0.58 KiB                                                                   0.37 KiB
  dist\css\chunk-vendors.190e707f.css      19.34 KiB                                                                  3.59 KiB
  dist\css\app.e32995c9.css                5.31 KiB                                                                   1.09 KiB
  dist\css\chunk-26af9b0f.26b9b620.css     0.31 KiB                                                                   0.19 KiB
  dist\css\chunk-374b839a.26b9b620.css     0.31 KiB                                                                   0.19 KiB
  dist\css\chunk-420adeb3.26b9b620.css     0.31 KiB                                                                   0.19 KiB

  Images and other types of assets omitted.

 DONE  Build complete. The dist directory is ready to be deployed.
 INFO  Check out deployment instructions at https://cli.vuejs.org/guide/deployment.html

> capacitor.cmd sync
[capacitor] (node:1492) ExperimentalWarning: Conditional exports is an experimental feature. This feature could change at any time
[capacitor] √ copy web in 512.30μp
[capacitor] √ update web in 48.30μp
[capacitor] [info] Sync finished in 0s
PS C:\Users\Me\Desktop\ionictest\ionic-android-bug>
PS C:\Users\Me\Desktop\ionictest\ionic-android-bug>
PS C:\Users\Me\Desktop\ionictest\ionic-android-bug>
PS C:\Users\Me\Desktop\ionictest\ionic-android-bug>
PS C:\Users\Me\Desktop\ionictest\ionic-android-bug>
PS C:\Users\Me\Desktop\ionictest\ionic-android-bug>
PS C:\Users\Me\Desktop\ionictest\ionic-android-bug>
PS C:\Users\Me\Desktop\ionictest\ionic-android-bug>
PS C:\Users\Me\Desktop\ionictest\ionic-android-bug>
PS C:\Users\Me\Desktop\ionictest\ionic-android-bug>
PS C:\Users\Me\Desktop\ionictest\ionic-android-bug> ionic cap run --verbose
  ionic:lib Terminal info: { ci: false, shell: 'C:\\WINDOWS\\system32\\cmd.exe', tty: true, windows: true } +0ms
  ionic:lib CLI global options: { _: [ 'cap', 'run' ], help: null, h: null, verbose: true, quiet: null, interactive: true, color: true, confirm: null, json: null, project: null, '--': [] } +10ms 
  ionic:lib:project Project type from config: @ionic/vue (vue) +0ms
  ionic:lib:project Project details: { context: 'app', type: 'vue', errors: [], configPath: 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\ionic.config.json' } +0ms
  ionic Context: { binPath: 'C:\\Users\\Me\\AppData\\Roaming\\npm\\node_modules\\@ionic\\cli\\bin\\ionic', libPath: 'C:\\Users\\Me\\AppData\\Roaming\\npm\\node_modules\\@ionic\\cli', execPath: 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug', version: '6.16.3' } +0ms
? What platform would you like to run? android
  ionic:lib:integrations:capacitor Getting config with Capacitor CLI: [ 'config', '--json' ] +0ms
  ionic:lib:integrations:capacitor Could not get config from Capacitor CLI (probably old version) +535ms
  ionic:commands:capacitor:run Getting native targets for 'android' with Capacitor CLI: [ 'run', 'android', '--list', '--json' ] +0ms
  ionic:commands:capacitor:run 2 native targets found +2s
? Which device would you like to target? OnePlus GM1917 (cbecde1b)
  ionic:lib:telemetry Sending telemetry for command: 'ionic capacitor run' [
  ionic:lib:telemetry   'android',
  ionic:lib:telemetry   '--verbose',
  ionic:lib:telemetry   '--interactive',
  ionic:lib:telemetry   '--color',
  ionic:lib:telemetry   '--target=cbecde1b'
  ionic:lib:telemetry ] +0ms
  ionic:lib:integrations:capacitor Capacitor config file does not exist at 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\capacitor.config.json' +7s
  ionic:lib:integrations:capacitor Failed to load Capacitor config +1ms
  ionic:lib:build build options: {
  ionic:lib:build   '--': [],
  ionic:lib:build   engine: 'capacitor',
  ionic:lib:build   platform: 'android',
  ionic:lib:build   project: undefined,
  ionic:lib:build   verbose: true,
  ionic:lib:build   type: 'vue'
  ionic:lib:build } +0ms
  ionic:lib:hooks Looking for ionic:build:before npm script. +0ms
  ionic:lib:build Looking for ionic:build npm script. +4ms
> vue-cli-service.cmd build
  vue:env C:\Users\Me\Desktop\ionictest\ionic-android-bug\.env.production.local {
  error: Error: ENOENT: no such file or directory, open 'C:\Users\Me\Desktop\ionictest\ionic-android-bug\.env.production.local'
      at Object.openSync (fs.js:457:3)
      at Object.readFileSync (fs.js:359:35)
      at Object.config (C:\Users\Me\Desktop\ionictest\ionic-android-bug\node_modules\dotenv\lib\main.js:96:29)
      at load (C:\Users\Me\Desktop\ionictest\ionic-android-bug\node_modules\@vue\cli-service\lib\Service.js:97:28)
      at Service.loadEnv (C:\Users\Me\Desktop\ionictest\ionic-android-bug\node_modules\@vue\cli-service\lib\Service.js:108:5)
      at Service.init (C:\Users\Me\Desktop\ionictest\ionic-android-bug\node_modules\@vue\cli-service\lib\Service.js:64:12)
      at Service.run (C:\Users\Me\Desktop\ionictest\ionic-android-bug\node_modules\@vue\cli-service\lib\Service.js:215:10)
      at Object.<anonymous> (C:\Users\Me\Desktop\ionictest\ionic-android-bug\node_modules\@vue\cli-service\bin\vue-cli-service.js:36:9)
      at Module._compile (internal/modules/cjs/loader.js:1151:30)
      at Object.Module._extensions..js (internal/modules/cjs/loader.js:1171:10) {
    errno: -4058,
    syscall: 'open',
    code: 'ENOENT',
    path: 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\.env.production.local'
  }
} +0ms
  vue:env C:\Users\Me\Desktop\ionictest\ionic-android-bug\.env.production {
  error: Error: ENOENT: no such file or directory, open 'C:\Users\Me\Desktop\ionictest\ionic-android-bug\.env.production'
      at Object.openSync (fs.js:457:3)
      at Object.readFileSync (fs.js:359:35)
      at Object.config (C:\Users\Me\Desktop\ionictest\ionic-android-bug\node_modules\dotenv\lib\main.js:96:29)
      at load (C:\Users\Me\Desktop\ionictest\ionic-android-bug\node_modules\@vue\cli-service\lib\Service.js:97:28)
      at Service.loadEnv (C:\Users\Me\Desktop\ionictest\ionic-android-bug\node_modules\@vue\cli-service\lib\Service.js:109:5)
      at Service.init (C:\Users\Me\Desktop\ionictest\ionic-android-bug\node_modules\@vue\cli-service\lib\Service.js:64:12)
      at Service.run (C:\Users\Me\Desktop\ionictest\ionic-android-bug\node_modules\@vue\cli-service\lib\Service.js:215:10)
      at Object.<anonymous> (C:\Users\Me\Desktop\ionictest\ionic-android-bug\node_modules\@vue\cli-service\bin\vue-cli-service.js:36:9)
      at Module._compile (internal/modules/cjs/loader.js:1151:30)
      at Object.Module._extensions..js (internal/modules/cjs/loader.js:1171:10) {
    errno: -4058,
    syscall: 'open',
    code: 'ENOENT',
    path: 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\.env.production'
  }
} +5ms
  vue:env C:\Users\Me\Desktop\ionictest\ionic-android-bug\.env.local {
  error: Error: ENOENT: no such file or directory, open 'C:\Users\Me\Desktop\ionictest\ionic-android-bug\.env.local'
      at Object.openSync (fs.js:457:3)
      at Object.readFileSync (fs.js:359:35)
      at Object.config (C:\Users\Me\Desktop\ionictest\ionic-android-bug\node_modules\dotenv\lib\main.js:96:29)
      at load (C:\Users\Me\Desktop\ionictest\ionic-android-bug\node_modules\@vue\cli-service\lib\Service.js:97:28)
      at Service.loadEnv (C:\Users\Me\Desktop\ionictest\ionic-android-bug\node_modules\@vue\cli-service\lib\Service.js:108:5)
      at Service.init (C:\Users\Me\Desktop\ionictest\ionic-android-bug\node_modules\@vue\cli-service\lib\Service.js:67:10)
      at Service.run (C:\Users\Me\Desktop\ionictest\ionic-android-bug\node_modules\@vue\cli-service\lib\Service.js:215:10)
      at Object.<anonymous> (C:\Users\Me\Desktop\ionictest\ionic-android-bug\node_modules\@vue\cli-service\bin\vue-cli-service.js:36:9)
      at Module._compile (internal/modules/cjs/loader.js:1151:30)
      at Object.Module._extensions..js (internal/modules/cjs/loader.js:1171:10) {
    errno: -4058,
    syscall: 'open',
    code: 'ENOENT',
    path: 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\.env.local'
  }
} +0ms
  vue:env C:\Users\Me\Desktop\ionictest\ionic-android-bug\.env {
  error: Error: ENOENT: no such file or directory, open 'C:\Users\Me\Desktop\ionictest\ionic-android-bug\.env'
      at Object.openSync (fs.js:457:3)
      at Object.readFileSync (fs.js:359:35)
      at Object.config (C:\Users\Me\Desktop\ionictest\ionic-android-bug\node_modules\dotenv\lib\main.js:96:29)
      at load (C:\Users\Me\Desktop\ionictest\ionic-android-bug\node_modules\@vue\cli-service\lib\Service.js:97:28)
      at Service.loadEnv (C:\Users\Me\Desktop\ionictest\ionic-android-bug\node_modules\@vue\cli-service\lib\Service.js:109:5)
      at Service.init (C:\Users\Me\Desktop\ionictest\ionic-android-bug\node_modules\@vue\cli-service\lib\Service.js:67:10)
      at Service.run (C:\Users\Me\Desktop\ionictest\ionic-android-bug\node_modules\@vue\cli-service\lib\Service.js:215:10)
      at Object.<anonymous> (C:\Users\Me\Desktop\ionictest\ionic-android-bug\node_modules\@vue\cli-service\bin\vue-cli-service.js:36:9)
      at Module._compile (internal/modules/cjs/loader.js:1151:30)
      at Object.Module._extensions..js (internal/modules/cjs/loader.js:1171:10) {
    errno: -4058,
    syscall: 'open',
    code: 'ENOENT',
    path: 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\.env'
  }
} +2ms
  vue:project-config {
  vue:project-config   publicPath: '/',
  vue:project-config   outputDir: 'dist',
  vue:project-config   assetsDir: '',
  vue:project-config   indexPath: 'index.html',
  vue:project-config   filenameHashing: true,
  vue:project-config   runtimeCompiler: false,
  vue:project-config   transpileDependencies: [],
  vue:project-config   productionSourceMap: true,
  vue:project-config   parallel: true,
  vue:project-config   pages: undefined,
  vue:project-config   crossorigin: undefined,
  vue:project-config   integrity: false,
  vue:project-config   css: {},
  vue:project-config   lintOnSave: 'default',
  vue:project-config   devServer: {}
  vue:project-config } +0ms
  babel:config:loading:files:configuration Found configuration 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\babel.config.js' from 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug'. +0ms
  babel:config:loading:files:plugins Loaded preset '@vue/cli-plugin-babel/preset' from 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug'. +0ms

-  Building for production...(node:16592) ExperimentalWarning: Conditional exports is an experimental feature. This feature could change at any time
/  Building for production...(node:11720) ExperimentalWarning: Conditional exports is an experimental feature. This feature could change at any time
-  Building for production...

 WARNING  Compiled with 1 warning                                                                                                                                                        5:01:14 PM
 warning 

entrypoint size limit: The following entrypoint(s) combined asset size exceeds the recommended limit (244 KiB). This can impact web performance.
Entrypoints:
  app (270 KiB)
      css/chunk-vendors.190e707f.css
      js/chunk-vendors.1d6b5269.js
      css/app.e32995c9.css
      js/app.ce460447.js


  File                                     Size                                                                       Gzipped  

  dist\js\chunk-vendors.1d6b5269.js        233.52 KiB                                                                 78.09 KiB
  dist\js\chunk-2d2297f7.78980670.js       101.07 KiB                                                                 26.96 KiB
  dist\js\polyfills-core-js.12be3461.js    91.91 KiB                                                                  30.28 KiB
  dist\js\chunk-5a8ac886.1c1bcfb0.js       62.67 KiB                                                                  8.02 KiB 
  dist\js\chunk-2d0a463b.580f9170.js       51.52 KiB                                                                  5.87 KiB 
  dist\js\chunk-53b1137a.8efb31cd.js       45.45 KiB                                                                  10.38 KiB
  dist\js\chunk-21a76241.9a71d653.js       44.48 KiB                                                                  10.96 KiB
  dist\js\chunk-1c4705f4.6dbe2887.js       38.09 KiB                                                                  7.06 KiB 
  dist\js\chunk-462c869e.0ea6ae2c.js       29.38 KiB                                                                  5.51 KiB 
  dist\js\chunk-d8413eac.9e3a3351.js       28.88 KiB                                                                  6.12 KiB 
  dist\js\chunk-25d83ca8.89659437.js       25.65 KiB                                                                  5.31 KiB 
  dist\js\chunk-a9395c36.8777d2b5.js       25.39 KiB                                                                  4.54 KiB 
  dist\js\chunk-426f2f16.9f46eefa.js       25.11 KiB                                                                  4.76 KiB 
  dist\js\chunk-5ff96a24.bc2c1407.js       23.22 KiB                                                                  4.34 KiB 
  dist\js\chunk-097e0872.3522b5ab.js       22.88 KiB                                                                  5.32 KiB 
  dist\js\chunk-3ed29de3.9e68e146.js       22.84 KiB                                                                  4.05 KiB
  dist\js\chunk-02c995b5.c8dee7ab.js       21.98 KiB                                                                  3.84 KiB
  dist\js\chunk-54bbd082.aa2ffdeb.js       21.02 KiB                                                                  4.72 KiB
  dist\js\chunk-1dbc15a2.8c41fb29.js       19.66 KiB                                                                  2.34 KiB
  dist\js\polyfills-dom.662760da.js        18.44 KiB                                                                  5.61 KiB
  dist\js\chunk-1bff95de.c7f1bfb8.js       16.78 KiB                                                                  4.37 KiB
  dist\js\chunk-37f2300e.cc3c45b7.js       16.37 KiB                                                                  3.58 KiB
  dist\js\chunk-7548ca2d.f50c2a89.js       16.10 KiB                                                                  3.45 KiB
  dist\js\chunk-41c0f7a4.5f0941d1.js       15.84 KiB                                                                  3.62 KiB
  dist\js\chunk-79f1dac7.4481f814.js       15.66 KiB                                                                  4.16 KiB
  dist\js\chunk-4739acd0.12a964e2.js       15.23 KiB                                                                  4.68 KiB
  dist\js\chunk-858cd918.54b9acef.js       14.95 KiB                                                                  4.65 KiB
  dist\js\chunk-eaa2b130.700c0fb3.js       14.67 KiB                                                                  2.91 KiB
  dist\js\chunk-69eb8776.8f434896.js       14.42 KiB                                                                  2.82 KiB
  dist\js\chunk-541ea42d.63c37d24.js       12.45 KiB                                                                  2.53 KiB
  dist\js\chunk-e5275ddc.a29be33a.js       12.19 KiB                                                                  3.48 KiB
  dist\js\chunk-0e93a01c.b0a5975b.js       12.01 KiB                                                                  3.03 KiB
  dist\js\app.ce460447.js                  11.91 KiB                                                                  4.04 KiB
  dist\js\chunk-2d0da04a.620f425b.js       11.71 KiB                                                                  1.75 KiB
  dist\js\chunk-6d375f34.8b250ad4.js       9.96 KiB                                                                   2.52 KiB
  dist\js\chunk-09162720.102e7a40.js       9.35 KiB                                                                   2.39 KiB
  dist\js\chunk-09155df3.e3ac211b.js       9.27 KiB                                                                   1.63 KiB
  dist\js\chunk-2d0d43da.c6672c38.js       8.84 KiB                                                                   3.11 KiB
  dist\js\chunk-2d217e6a.9d5e5387.js       8.72 KiB                                                                   3.48 KiB
  dist\js\chunk-d0e8aa0a.ef2f5d14.js       7.58 KiB                                                                   2.53 KiB
  dist\js\chunk-8bb7f81e.4465b78a.js       7.32 KiB                                                                   2.04 KiB
  dist\js\chunk-2d21da73.56e20878.js       6.72 KiB                                                                   1.76 KiB
  dist\js\chunk-2d213189.2b11f265.js       6.70 KiB                                                                   1.55 KiB
  dist\js\chunk-47245a33.b9e6a322.js       6.33 KiB                                                                   1.96 KiB
  dist\js\chunk-2d237b00.037b5772.js       5.53 KiB                                                                   2.36 KiB
  dist\js\chunk-2d0b9280.58416f48.js       5.43 KiB                                                                   2.10 KiB
  dist\js\chunk-59d4c87c.9a2960ba.js       4.81 KiB                                                                   1.30 KiB
  dist\js\chunk-2d0d5c33.d98bbfcf.js       3.92 KiB                                                                   1.65 KiB
  dist\js\chunk-2d218068.115cead1.js       3.53 KiB                                                                   1.17 KiB
  dist\js\chunk-26af9b0f.908002a9.js       2.22 KiB                                                                   0.86 KiB
  dist\js\chunk-374b839a.68a7c833.js       2.22 KiB                                                                   0.87 KiB
  dist\js\chunk-420adeb3.5b70ee52.js       2.22 KiB                                                                   0.87 KiB
  dist\js\chunk-2d0baac9.ecbd8a2b.js       2.17 KiB                                                                   0.96 KiB
  dist\js\chunk-2d0e5812.bc3079e1.js       1.87 KiB                                                                   0.76 KiB
  dist\js\chunk-2d0c073f.017f6960.js       1.77 KiB                                                                   0.72 KiB
  dist\js\chunk-2d2376e6.a05b70ee.js       1.71 KiB                                                                   0.69 KiB
  dist\js\chunk-30dd9750.6b7d6eb0.js       1.43 KiB                                                                   0.70 KiB
  dist\js\chunk-2d0b33e3.2e69defc.js       0.91 KiB                                                                   0.47 KiB
  dist\js\chunk-2d0c9758.62f099a9.js       0.75 KiB                                                                   0.49 KiB
  dist\js\chunk-2d0b9074.cf6d8bbf.js       0.58 KiB                                                                   0.37 KiB
  dist\css\chunk-vendors.190e707f.css      19.34 KiB                                                                  3.59 KiB
  dist\css\app.e32995c9.css                5.31 KiB                                                                   1.09 KiB
  dist\css\chunk-26af9b0f.26b9b620.css     0.31 KiB                                                                   0.19 KiB
  dist\css\chunk-374b839a.26b9b620.css     0.31 KiB                                                                   0.19 KiB
  dist\css\chunk-420adeb3.26b9b620.css     0.31 KiB                                                                   0.19 KiB

  Images and other types of assets omitted.

 DONE  Build complete. The dist directory is ready to be deployed.
 INFO  Check out deployment instructions at https://cli.vuejs.org/guide/deployment.html

  ionic:lib:hooks Looking for ionic:build:after npm script. +26s
  ionic:lib:hooks Looking for ionic:capacitor:run:before npm script. +2ms
> capacitor.cmd run android --target cbecde1b
[capacitor] (node:2216) ExperimentalWarning: Conditional exports is an experimental feature. This feature could change at any time
[capacitor] 2021-06-10T22:01:16.610Z capacitor:config config: {
[capacitor]   android: {
[capacitor]     name: 'android',
[capacitor]     minVersion: '21',
[capacitor]     studioPath: LazyPromise [Promise] {
[capacitor]       <pending>,
[capacitor]       _executor: [AsyncFunction (anonymous)]
[capacitor]     },
[capacitor]     platformDir: 'android',
[capacitor]     platformDirAbs: 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\android',
[capacitor]     cordovaPluginsDir: 'capacitor-cordova-android-plugins',
[capacitor]     cordovaPluginsDirAbs: 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\android\\capacitor-cordova-android-plugins',
[capacitor]     appDir: 'app',
[capacitor]     appDirAbs: 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\android\\app',
[capacitor]     srcDir: 'app/src',
[capacitor]     srcDirAbs: 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\android\\app\\src',
[capacitor]     srcMainDir: 'app/src/main',
[capacitor]     srcMainDirAbs: 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\android\\app\\src\\main',
[capacitor]     assetsDir: 'app/src/main/assets',
[capacitor]     assetsDirAbs: 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\android\\app\\src\\main\\assets',
[capacitor]     webDir: 'app/src/main/assets/public',
[capacitor]     webDirAbs: 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\android\\app\\src\\main\\assets\\public',
[capacitor]     resDir: 'app/src/main/res',
[capacitor]     resDirAbs: 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\android\\app\\src\\main\\res',
[capacitor]     buildOutputDir: 'app/build/outputs/apk/debug',
[capacitor]     buildOutputDirAbs: 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\android\\app\\build\\outputs\\apk\\debug'
[capacitor]   },
[capacitor]   ios: {
[capacitor]     name: 'ios',
[capacitor]     minVersion: '12.0',
[capacitor]     platformDir: 'ios',
[capacitor]     platformDirAbs: 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\ios',
[capacitor]     scheme: 'App',
[capacitor]     cordovaPluginsDir: 'capacitor-cordova-ios-plugins',
[capacitor]     cordovaPluginsDirAbs: 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\ios\\capacitor-cordova-ios-plugins',
[capacitor]     nativeProjectDir: 'App',
[capacitor]     nativeProjectDirAbs: 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\ios\\App',
[capacitor]     nativeTargetDir: 'App/App',
[capacitor]     nativeTargetDirAbs: 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\ios\\App\\App',
[capacitor]     nativeXcodeProjDir: 'App/App.xcodeproj',
[capacitor]     nativeXcodeProjDirAbs: 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\ios\\App\\App.xcodeproj',
[capacitor]     nativeXcodeWorkspaceDir: LazyPromise [Promise] {
[capacitor]       <pending>,
[capacitor]       _executor: [AsyncFunction (anonymous)]
[capacitor]     },
[capacitor]     nativeXcodeWorkspaceDirAbs: LazyPromise [Promise] {
[capacitor]       <pending>,
[capacitor]       _executor: [AsyncFunction (anonymous)]
[capacitor]     },
[capacitor]     webDir: LazyPromise [Promise] {
[capacitor]       <pending>,
[capacitor]       _executor: [AsyncFunction (anonymous)]
[capacitor]     },
[capacitor]     webDirAbs: LazyPromise [Promise] {
[capacitor]       <pending>,
[capacitor]       _executor: [AsyncFunction (anonymous)]
[capacitor]     },
[capacitor]     podPath: 'pod'
[capacitor]   },
[capacitor]   web: {
[capacitor]     name: 'web',
[capacitor]     platformDir: 'dist',
[capacitor]     platformDirAbs: 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\dist'
[capacitor]   },
[capacitor]   cli: {
[capacitor]     rootDir: 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\node_modules\\@capacitor\\cli',
[capacitor]     assetsDir: 'assets',
[capacitor]     assetsDirAbs: 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\node_modules\\@capacitor\\cli\\assets',
[capacitor]     assets: { ios: [Object], android: [Object] },
[capacitor]     package: {
[capacitor]       name: '@capacitor/cli',
[capacitor]       version: '3.0.1',
[capacitor]       description: 'Capacitor: Cross-platform apps with JavaScript and the web',
[capacitor]       homepage: 'https://capacitorjs.com',
[capacitor]       author: 'Ionic Team <hi@ionic.io> (https://ionic.io)',
[capacitor]       license: 'MIT',
[capacitor]       repository: [Object],
[capacitor]       bugs: [Object],
[capacitor]       files: [Array],
[capacitor]       keywords: [Array],
[capacitor]       engines: [Object],
[capacitor]       main: 'dist/index.js',
[capacitor]       types: 'dist/declarations.d.ts',
[capacitor]       bin: [Object],
[capacitor]       scripts: [Object],
[capacitor]       dependencies: [Object],
[capacitor]       devDependencies: [Object],
[capacitor]       jest: [Object],
[capacitor]       publishConfig: [Object],
[capacitor]       gitHead: '59b05820dcb0dc76885cb25354a15fb75076fb5b'
[capacitor]     },
[capacitor]     os: 'windows'
[capacitor]   },
[capacitor]   app: {
[capacitor]     rootDir: 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug',
[capacitor]     appId: 'io.ionic.starter',
[capacitor]     appName: 'ionic-android-bug',
[capacitor]     webDir: 'dist',
[capacitor]     webDirAbs: 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\dist',
[capacitor]     package: {
[capacitor]       name: 'ionic-android-bug',
[capacitor]       version: '0.0.1',
[capacitor]       private: true,
[capacitor]       scripts: [Object],
[capacitor]       dependencies: [Object],
[capacitor]       devDependencies: [Object],
[capacitor]       description: 'An Ionic project'
[capacitor]     },
[capacitor]     extConfigType: 'ts',
[capacitor]     extConfigName: 'capacitor.config.ts',
[capacitor]     extConfigFilePath: 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\capacitor.config.ts',
[capacitor]     extConfig: {
[capacitor]       appId: 'io.ionic.starter',
[capacitor]       appName: 'ionic-android-bug',
[capacitor]       webDir: 'dist',
[capacitor]       bundledWebRuntime: false
[capacitor]     },
[capacitor]     bundledWebRuntime: false
[capacitor]   }
[capacitor] }
[capacitor] √ Copying web assets from dist to android\app\src\main\assets\public in 15.33s
[capacitor] √ Creating capacitor.config.json in android\app\src\main\assets in 1.32ms
[capacitor] √ copy android in 15.36s
[capacitor] √ Updating Android plugins in 3.71ms
[capacitor] [info] Found 4 Capacitor plugins for android:
[capacitor]        @capacitor/app@1.0.1
[capacitor]        @capacitor/haptics@1.0.1
[capacitor]        @capacitor/keyboard@1.0.1
[capacitor]        @capacitor/status-bar@1.0.1
[capacitor] 2021-06-10T22:01:32.205Z capacitor:android:update Searching 1 source files in 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\node_modules\\@capacitor\\app\\android\\src\\main' by /^@(?:CapacitorPlugin|NativePlugin)[\s\S]+?class ([\w]+)/gm regex
[capacitor] 2021-06-10T22:01:32.206Z capacitor:android:update Searching 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\node_modules\\@capacitor\\app\\android\\src\\main\\java\\com\\capacitorjs\\plugins\\app\\AppPlugin.java' for package by /^package ([\w.]+);?$/gm regex
[capacitor] 2021-06-10T22:01:32.206Z capacitor:android:update 'com.capacitorjs.plugins.app.AppPlugin' is a suitable plugin class
[capacitor] 2021-06-10T22:01:32.211Z capacitor:android:update Searching 6 source files in 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\node_modules\\@capacitor\\haptics\\android\\src\\main' by /^@(?:CapacitorPlugin|NativePlugin)[\s\S]+?class ([\w]+)/gm regex
[capacitor] 2021-06-10T22:01:32.211Z capacitor:android:update Searching 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\node_modules\\@capacitor\\haptics\\android\\src\\main\\java\\com\\capacitorjs\\plugins\\haptics\\HapticsPlugin.java' for package by /^package ([\w.]+);?$/gm regex
[capacitor] 2021-06-10T22:01:32.212Z capacitor:android:update 'com.capacitorjs.plugins.haptics.HapticsPlugin' is a suitable plugin class
[capacitor] 2021-06-10T22:01:32.216Z capacitor:android:update Searching 2 source files in 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\node_modules\\@capacitor\\keyboard\\android\\src\\main' by /^@(?:CapacitorPlugin|NativePlugin)[\s\S]+?class ([\w]+)/gm regex
[capacitor] 2021-06-10T22:01:32.216Z capacitor:android:update Searching 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\node_modules\\@capacitor\\keyboard\\android\\src\\main\\java\\com\\capacitorjs\\plugins\\keyboard\\KeyboardPlugin.java' for package by /^package ([\w.]+);?$/gm regex
[capacitor] 2021-06-10T22:01:32.216Z capacitor:android:update 'com.capacitorjs.plugins.keyboard.KeyboardPlugin' is a suitable plugin class
[capacitor] 2021-06-10T22:01:32.220Z capacitor:android:update Searching 3 source files in 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\node_modules\\@capacitor\\status-bar\\android\\src\\main' by /^@(?:CapacitorPlugin|NativePlugin)[\s\S]+?class ([\w]+)/gm regex
[capacitor] 2021-06-10T22:01:32.220Z capacitor:android:update Searching 'C:\\Users\\Me\\Desktop\\ionictest\\ionic-android-bug\\node_modules\\@capacitor\\status-bar\\android\\src\\main\\java\\com\\capacitorjs\\plugins\\statusbar\\StatusBarPlugin.java' for package by /^package ([\w.]+);?$/gm regex
[capacitor] 2021-06-10T22:01:32.220Z capacitor:android:update 'com.capacitorjs.plugins.statusbar.StatusBarPlugin' is a suitable plugin class
[capacitor] √ update android in 111.56ms
[capacitor] 2021-06-10T22:01:34.422Z capacitor:android:run Invoking ./gradlew with args: [ 'assembleDebug' ]
[capacitor] × Running Gradle build - failed!
[capacitor] [error] 
[capacitor]         C:\Users\Me\Desktop\ionictest\ionic-android-bug\android>if "Windows_NT" == "Windows_NT" setlocal
[capacitor]
[capacitor]         C:\Users\Me\Desktop\ionictest\ionic-android-bug\android>set DIRNAME=C:\Users\Me\Desktop\ionictest\ionic-android-bug\android\
[capacitor]
[capacitor]         C:\Users\Me\Desktop\ionictest\ionic-android-bug\android>if "C:\Users\Me\Desktop\ionictest\ionic-android-bug\android\" == "" set DIRNAME=.
[capacitor]
[capacitor]         C:\Users\Me\Desktop\ionictest\ionic-android-bug\android>set APP_BASE_NAME=gradlew
[capacitor]
[capacitor]         C:\Users\Me\Desktop\ionictest\ionic-android-bug\android>set APP_HOME=C:\Users\Me\Desktop\ionictest\ionic-android-bug\android\
[capacitor]
[capacitor]         C:\Users\Me\Desktop\ionictest\ionic-android-bug\android>for %i in ("C:\Users\Me\Desktop\ionictest\ionic-android-bug\android\") do set APP_HOME=%~fi
[capacitor]
[capacitor]         C:\Users\Me\Desktop\ionictest\ionic-android-bug\android>set APP_HOME=C:\Users\Me\Desktop\ionictest\ionic-android-bug\android\
[capacitor]
[capacitor]         C:\Users\Me\Desktop\ionictest\ionic-android-bug\android>set DEFAULT_JVM_OPTS="-Xmx64m" "-Xms64m"
[capacitor]
[capacitor]         C:\Users\Me\Desktop\ionictest\ionic-android-bug\android>if defined JAVA_HOME goto findJavaFromJavaHome
[capacitor]
[capacitor]         C:\Users\Me\Desktop\ionictest\ionic-android-bug\android>set JAVA_HOME=C:\Program Files\Java\jdk-16.0.1
[capacitor]
[capacitor]         C:\Users\Me\Desktop\ionictest\ionic-android-bug\android>set JAVA_EXE=C:\Program Files\Java\jdk-16.0.1/bin/java.exe
[capacitor]
[capacitor]         C:\Users\Me\Desktop\ionictest\ionic-android-bug\android>if exist "C:\Program Files\Java\jdk-16.0.1/bin/java.exe" goto execute
[capacitor]
[capacitor]         C:\Users\Me\Desktop\ionictest\ionic-android-bug\android>set CLASSPATH=C:\Users\Me\Desktop\ionictest\ionic-android-bug\android\\gradle\wrapper\gradle-wrapper.jar
[capacitor]
[capacitor]         C:\Users\Me\Desktop\ionictest\ionic-android-bug\android>"C:\Program Files\Java\jdk-16.0.1/bin/java.exe" "-Xmx64m" "-Xms64m"   "-Dorg.gradle.appname=gradlew" -classpath "C:\Users\Me\Desktop\ionictest\ionic-android-bug\android\\gradle\wrapper\gradle-wrapper.jar" org.gradle.wrapper.GradleWrapperMain "assembleDebug"
[capacitor]
[capacitor]         > Configure project :app
[capacitor]         google-services.json not found, google-services plugin not applied. Push Notifications won't work
[capacitor]         WARNING:: Using flatDirs should be avoided because it doesn't support any meta-data formats.
[capacitor]         Currently detected usages:
[capacitor]         - repository flatDir used in: project ':app', project ':capacitor-cordova-android-plugins'
[capacitor]         WARNING:: Please remove usages of `jcenter()` Maven repository from your build scripts and migrate your build to other Maven repositories.
[capacitor]         This repository is deprecated and it will be shut down in the future.
[capacitor]         See http://developer.android.com/r/tools/jcenter-end-of-service for more information.
[capacitor]         Currently detected usages in: root project 'android', project ':app', project ':capacitor-android', ...
[capacitor]
[capacitor]         > Task :app:preBuild UP-TO-DATE
[capacitor]         > Task :app:preDebugBuild UP-TO-DATE
[capacitor]         > Task :capacitor-android:preBuild UP-TO-DATE
[capacitor]         > Task :capacitor-android:preDebugBuild UP-TO-DATE
[capacitor]         > Task :capacitor-android:compileDebugAidl NO-SOURCE
[capacitor]         > Task :capacitor-app:preBuild UP-TO-DATE
[capacitor]         > Task :capacitor-app:preDebugBuild UP-TO-DATE
[capacitor]         > Task :capacitor-app:compileDebugAidl NO-SOURCE
[capacitor]         > Task :capacitor-cordova-android-plugins:preBuild UP-TO-DATE
[capacitor]         > Task :capacitor-cordova-android-plugins:preDebugBuild UP-TO-DATE
[capacitor]         > Task :capacitor-cordova-android-plugins:compileDebugAidl NO-SOURCE
[capacitor]         > Task :capacitor-haptics:preBuild UP-TO-DATE
[capacitor]         > Task :capacitor-haptics:preDebugBuild UP-TO-DATE
[capacitor]         > Task :capacitor-haptics:compileDebugAidl NO-SOURCE
[capacitor]         > Task :capacitor-keyboard:preBuild UP-TO-DATE
[capacitor]         > Task :capacitor-keyboard:preDebugBuild UP-TO-DATE
[capacitor]         > Task :capacitor-keyboard:compileDebugAidl NO-SOURCE
[capacitor]         > Task :capacitor-status-bar:preBuild UP-TO-DATE
[capacitor]         > Task :capacitor-status-bar:preDebugBuild UP-TO-DATE
[capacitor]         > Task :capacitor-status-bar:compileDebugAidl NO-SOURCE
[capacitor]         > Task :app:compileDebugAidl NO-SOURCE
[capacitor]         > Task :capacitor-android:packageDebugRenderscript NO-SOURCE
[capacitor]         > Task :capacitor-app:packageDebugRenderscript NO-SOURCE
[capacitor]         > Task :capacitor-cordova-android-plugins:packageDebugRenderscript NO-SOURCE
[capacitor]         > Task :capacitor-haptics:packageDebugRenderscript NO-SOURCE
[capacitor]         > Task :capacitor-keyboard:packageDebugRenderscript NO-SOURCE
[capacitor]         > Task :capacitor-status-bar:packageDebugRenderscript NO-SOURCE
[capacitor]         > Task :app:compileDebugRenderscript NO-SOURCE
[capacitor]         > Task :app:generateDebugBuildConfig UP-TO-DATE
[capacitor]         > Task :app:javaPreCompileDebug UP-TO-DATE
[capacitor]         > Task :capacitor-android:writeDebugAarMetadata UP-TO-DATE
[capacitor]         > Task :capacitor-app:writeDebugAarMetadata UP-TO-DATE
[capacitor]         > Task :capacitor-haptics:writeDebugAarMetadata UP-TO-DATE
[capacitor]         > Task :capacitor-keyboard:writeDebugAarMetadata UP-TO-DATE
[capacitor]         > Task :capacitor-cordova-android-plugins:writeDebugAarMetadata
[capacitor]         > Task :capacitor-status-bar:writeDebugAarMetadata UP-TO-DATE
[capacitor]         > Task :app:generateDebugResValues UP-TO-DATE
[capacitor]         > Task :app:generateDebugResources UP-TO-DATE
[capacitor]         > Task :capacitor-android:compileDebugRenderscript NO-SOURCE
[capacitor]         > Task :capacitor-android:generateDebugResValues UP-TO-DATE
[capacitor]         > Task :capacitor-android:generateDebugResources UP-TO-DATE
[capacitor]         > Task :capacitor-android:packageDebugResources UP-TO-DATE
[capacitor]         > Task :capacitor-app:compileDebugRenderscript NO-SOURCE
[capacitor]         > Task :capacitor-app:generateDebugResValues UP-TO-DATE
[capacitor]         > Task :capacitor-app:generateDebugResources UP-TO-DATE
[capacitor]         > Task :capacitor-app:packageDebugResources UP-TO-DATE
[capacitor]         > Task :capacitor-cordova-android-plugins:compileDebugRenderscript NO-SOURCE
[capacitor]         > Task :capacitor-cordova-android-plugins:generateDebugResValues
[capacitor]         > Task :capacitor-cordova-android-plugins:generateDebugResources
[capacitor]         > Task :capacitor-cordova-android-plugins:packageDebugResources
[capacitor]         > Task :capacitor-haptics:compileDebugRenderscript NO-SOURCE
[capacitor]         > Task :capacitor-haptics:generateDebugResValues UP-TO-DATE
[capacitor]         > Task :capacitor-haptics:generateDebugResources UP-TO-DATE
[capacitor]         > Task :capacitor-haptics:packageDebugResources UP-TO-DATE
[capacitor]         > Task :capacitor-keyboard:compileDebugRenderscript NO-SOURCE
[capacitor]         > Task :capacitor-keyboard:generateDebugResValues UP-TO-DATE
[capacitor]         > Task :capacitor-keyboard:generateDebugResources UP-TO-DATE
[capacitor]         > Task :capacitor-keyboard:packageDebugResources UP-TO-DATE
[capacitor]         > Task :capacitor-status-bar:compileDebugRenderscript NO-SOURCE
[capacitor]         > Task :capacitor-status-bar:generateDebugResValues UP-TO-DATE
[capacitor]         > Task :capacitor-status-bar:generateDebugResources UP-TO-DATE
[capacitor]         > Task :capacitor-status-bar:packageDebugResources UP-TO-DATE
[capacitor]         > Task :app:mergeDebugResources UP-TO-DATE
[capacitor]         > Task :app:createDebugCompatibleScreenManifests UP-TO-DATE
[capacitor]         > Task :app:extractDeepLinksDebug UP-TO-DATE
[capacitor]         > Task :capacitor-android:extractDeepLinksDebug UP-TO-DATE
[capacitor]         > Task :capacitor-android:processDebugManifest UP-TO-DATE
[capacitor]         > Task :capacitor-app:extractDeepLinksDebug UP-TO-DATE
[capacitor]         > Task :capacitor-app:processDebugManifest UP-TO-DATE
[capacitor]         > Task :capacitor-cordova-android-plugins:extractDeepLinksDebug
[capacitor]         > Task :capacitor-haptics:extractDeepLinksDebug UP-TO-DATE
[capacitor]         > Task :capacitor-haptics:processDebugManifest UP-TO-DATE
[capacitor]         > Task :capacitor-keyboard:extractDeepLinksDebug UP-TO-DATE
[capacitor]         > Task :capacitor-keyboard:processDebugManifest UP-TO-DATE
[capacitor]         > Task :capacitor-status-bar:extractDeepLinksDebug UP-TO-DATE
[capacitor]         > Task :capacitor-status-bar:processDebugManifest UP-TO-DATE
[capacitor]         > Task :capacitor-cordova-android-plugins:processDebugManifest
[capacitor]         > Task :capacitor-android:compileDebugLibraryResources UP-TO-DATE
[capacitor]         > Task :capacitor-android:parseDebugLocalResources UP-TO-DATE
[capacitor]         > Task :capacitor-android:generateDebugRFile UP-TO-DATE
[capacitor]         > Task :capacitor-app:compileDebugLibraryResources UP-TO-DATE
[capacitor]         > Task :capacitor-app:parseDebugLocalResources UP-TO-DATE
[capacitor]         > Task :capacitor-cordova-android-plugins:compileDebugLibraryResources
[capacitor]         > Task :capacitor-cordova-android-plugins:parseDebugLocalResources
[capacitor]
[capacitor]         FAILURE: Build failed with an exception.
[capacitor]
[capacitor]         * What went wrong:
[capacitor]         Execution failed for task ':app:processDebugMainManifest'.
[capacitor]         > Task :capacitor-app:generateDebugRFile
[capacitor]         > Task :app:processDebugMainManifest FAILED
[capacitor]         > Unable to make field private final java.lang.String java.io.File.path accessible: module java.base does not "opens java.io" to unnamed module @22738b3d
[capacitor]
[capacitor]         * Try:
[capacitor]         Run with --stacktrace option to get the stack trace. Run with --info or --debug option to get more log output. Run with --scan to get full insights.
[capacitor]
[capacitor]         * Get more help at https://help.gradle.org
[capacitor]
[capacitor]         Deprecated Gradle features were used in this build, making it incompatible with Gradle 8.0.
[capacitor]         Use '--warning-mode all' to show the individual deprecation warnings.
[capacitor]         See https://docs.gradle.org/7.0/userguide/command_line_interface.html#sec:command_line_warnings
[capacitor]         BUILD FAILED in 1s
[capacitor]
[capacitor]         45 actionable tasks: 9 executed, 36 up-to-date
[capacitor]
[capacitor]         C:\Users\Me\Desktop\ionictest\ionic-android-bug\android>if "1" == "0" goto mainEnd
[capacitor]
[capacitor]         C:\Users\Me\Desktop\ionictest\ionic-android-bug\android>rem Set variable GRADLE_EXIT_CONSOLE if you need the _script_ return code instead of
[capacitor]
[capacitor]         C:\Users\Me\Desktop\ionictest\ionic-android-bug\android>rem the _cmd.exe /c_ return code!
[capacitor]
[capacitor]         C:\Users\Me\Desktop\ionictest\ionic-android-bug\android>if not "" == "" exit 1
[capacitor]
[capacitor]         C:\Users\Me\Desktop\ionictest\ionic-android-bug\android>exit /b 1
[capacitor]
[ERROR] An error occurred while running subprocess capacitor.

        capacitor.cmd run android --target cbecde1b exited with exit code 1.

        Re-running this command with the --verbose flag may provide more information.
  ionic:utils-process onBeforeExit handler: 'process.exit' received +0ms
  ionic:utils-process onBeforeExit handler: running 2 functions +0ms
  ionic:utils-process error while killing process tree for 8692: Error: Command failed: taskkill /pid 8692 /T /F
  ionic:utils-process ERROR: The process "8692" not found.
  ionic:utils-process 
  ionic:utils-process     at ChildProcess.exithandler (child_process.js:303:12)
  ionic:utils-process     at ChildProcess.emit (events.js:321:20)
  ionic:utils-process     at maybeClose (internal/child_process.js:1026:16)
  ionic:utils-process     at Process.ChildProcess._handle.onexit (internal/child_process.js:286:5) {
  ionic:utils-process   killed: false,
  ionic:utils-process   code: 128,
  ionic:utils-process   signal: null,
  ionic:utils-process   cmd: 'taskkill /pid 8692 /T /F'
  ionic:utils-process } +151ms
  ionic:utils-process onBeforeExit handler: error from function: Error: Command failed: taskkill /pid 8692 /T /F
  ionic:utils-process ERROR: The process "8692" not found.
  ionic:utils-process 
  ionic:utils-process     at ChildProcess.exithandler (child_process.js:303:12)
  ionic:utils-process     at ChildProcess.emit (events.js:321:20)
  ionic:utils-process     at maybeClose (internal/child_process.js:1026:16)
  ionic:utils-process     at Process.ChildProcess._handle.onexit (internal/child_process.js:286:5) {
  ionic:utils-process   killed: false,
  ionic:utils-process   code: 128,
  ionic:utils-process   signal: null,
  ionic:utils-process   cmd: 'taskkill /pid 8692 /T /F'
  ionic:utils-process } +3ms
  ionic:utils-process error while killing process tree for 16296: Error: Command failed: taskkill /pid 16296 /T /F
  ionic:utils-process ERROR: The process "16296" not found.
  ionic:utils-process 
  ionic:utils-process     at ChildProcess.exithandler (child_process.js:303:12)
  ionic:utils-process     at ChildProcess.emit (events.js:321:20)
  ionic:utils-process     at maybeClose (internal/child_process.js:1026:16)
  ionic:utils-process     at Process.ChildProcess._handle.onexit (internal/child_process.js:286:5) {
  ionic:utils-process   killed: false,
  ionic:utils-process   code: 128,
  ionic:utils-process   signal: null,
  ionic:utils-process   cmd: 'taskkill /pid 16296 /T /F'
  ionic:utils-process } +1ms
  ionic:utils-process onBeforeExit handler: error from function: Error: Command failed: taskkill /pid 16296 /T /F
  ionic:utils-process ERROR: The process "16296" not found.
  ionic:utils-process 
  ionic:utils-process     at ChildProcess.exithandler (child_process.js:303:12)
  ionic:utils-process     at ChildProcess.emit (events.js:321:20)
  ionic:utils-process     at maybeClose (internal/child_process.js:1026:16)
  ionic:utils-process     at Process.ChildProcess._handle.onexit (internal/child_process.js:286:5) {
  ionic:utils-process   killed: false,
  ionic:utils-process   code: 128,
  ionic:utils-process   signal: null,
  ionic:utils-process   cmd: 'taskkill /pid 16296 /T /F'
  ionic:utils-process } +2ms
  ionic:utils-process processExit: exiting (exit code: 1) +1ms
```
