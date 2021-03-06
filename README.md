# README

## Clone project

```shell
git clone https://github.com/solidarynetwork/solidarynetwork-mobile-android-scom-citizencard-starter.git
```

## Create encoded license secrets file

1. create a file with your encodeLicense named `secrets.properties` in the root of the project
2. add `secrets.properties` to `.gitignore`

ex.

```
encodedLicense="YOUR-ENCODED-LICENSE-HERE"
```

## Install AAR SCom SDK Dependency

> request your copy of SCom SDK from authors at [scom.pt](https://scom.pt)

> our SDK was kindly donated for our solidarity project only, **thanks to all the good people** at [scom.pt](https://scom.pt)

1. create `libs/` folder in `app/libs`
2. copy `cc-android-sdk-1.6.0.aar` to `app/libs` folder
3. add `app/libs` to `.gitignore`
4. add `libs/cc-android-sdk-1.6.0.aar` to `app/build.gradle`
5. update `android/app/build.gradle` with `cc-android-sdk`, `gson` and `okhttp` (this step is already done, only here for reference)


```
repositories {
  flatDir {
    dirs 'libs'
  }
}

dependencies {
  ...
  implementation files('libs/cc-android-sdk-1.6.0.aar')
  implementation 'com.google.code.gson:gson:2.8.5'
  implementation("com.squareup.okhttp3:okhttp:4.2.2")
}
```

5. sync project
6. run project

> SCom SDK requires gson and okhttp

## Change project name and package name

1. search all `network.solidary.mobile` occurrences and change with your own reverse domain name ex `com.acme.mobile`

`app/src/main/AndroidManifest.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
  package="network.solidary.mobile">
```

2. replace `app_name`

`values/strings.xml`

```xml
<string name="app_name">SNCitizenCard</string>
```

3. refactor package name

```
network.solidary.mobile.MainActivity
```

```java
package network.solidary.mobile;
```
