---
layout: project
type: android-library
title: "Attribouter"
description: "A lightweight \"about screen\" library to allow quick but customizable attribution in Android apps."
repo: fennifith/Attribouter
git: git://github.com/fennifith/Attribouter.git
links:
  - name: GitHub
    url: https://github.com/fennifith/Attribouter
    icon: https://github.com/favicon.ico
  - name: Issues
    url: https://github.com/fennifith/Attribouter/issues
    icon: /images/ic/bug.svg
  - name: Apache License 2.0
    url: https://choosealicense.com/licenses/apache-2.0/
    icon: /images/ic/copyright.svg
  - name: JitPack
    url: https://jitpack.io/#me.jfenn/Attribouter
    icon: /images/ic/launch.svg
  - name: Attribouter.apk (0.1.5 stable)
    url: https://github.com/fennifith/Attribouter/releases/download/0.1.5/Attribouter.apk
    icon: /images/ic/download.svg
contributors:
  - login: fennifith
    avatar: https://avatars1.githubusercontent.com/u/13000407?v=4
    url: https://github.com/fennifith
  - login: divadsn
    avatar: https://avatars2.githubusercontent.com/u/28547847?v=4
    url: https://github.com/divadsn
  - login: gcantoni
    avatar: https://avatars0.githubusercontent.com/u/30368951?v=4
    url: https://github.com/gcantoni
  - login: rroyGit
    avatar: https://avatars2.githubusercontent.com/u/20290568?v=4
    url: https://github.com/rroyGit
isDocs: true
isWiki: true
languages:
  - Java
pushed: 2018-11-21T15:24:31Z
---

Attribouter is a lightweight "about screen" for Android apps, built to allow developers to easily give credit to a project's contributors and open source libraries, while matching the style of their app and saving the largest amount of time and effort possible. It is meant to use GitHub's [REST API](https://developer.github.com/v3/) to fetch and display information about open source projects and contributors, but it allows you to define some or all of its data in its configuration file in your app as well.

[![](https://jitpack.io/v/me.jfenn/Attribouter.svg)](https://jitpack.io/#me.jfenn/Attribouter)
[![Discord](https://img.shields.io/discord/514625116706177035.svg)](https://discord.gg/amDKN6A)

### Screenshots

This is just sample data. It is not real. Though Jahir is lazy, so that part is (joking).

|Contributors|Contributor|Licenses|License|
|-----|-----|-----|-----|
|![img](https://jfenn.me/images/screenshots/Attribouter-Main.png)|![img](https://jfenn.me/images/screenshots/Attribouter-Contributor.png)|![img](https://jfenn.me/images/screenshots/Attribouter-Licenses.png)|![img](https://jfenn.me/images/screenshots/Attribouter-License.png)|

### APK

For demonstration and experimentation, an apk of the sample project can be downloaded [here](https://github.com/fennifith/Attribouter/blob/master/../../releases/).

## Usage

This project is published on [JitPack](https://jitpack.io), which you can add to your project by copying the following to your root build.gradle at the end of "repositories".

```gradle
allprojects {
  repositories {
    ...
    maven { url 'https://jitpack.io' }
  }
}
```

To add the dependency, copy this line into your app module's build.gradle file.

```gradle
implementation 'me.jfenn:Attribouter:0.1.5'
```

##### Support Libraries

The Android support libraries have been refactored from `android.support.*` to `androidx.*` as detailed [here](https://developer.android.com/topic/libraries/support-library/androidx-overview). As such, Attribouter only uses the new dependencies. If your project still uses the older support libraries for some reason, you may either compile your own version of Attribouter or use the last version to use the old support libraries, `0.1.2`.

### Starting an Activity
This is pretty simple.

``` java
Attribouter.from(context).show();
```

### Creating a Fragment
This is also pretty simple.

``` java
Fragment fragment = Attribouter.from(context).toFragment();
```

## Request Limits

This library does not use an auth key for the GitHub API by default. It does cache data for up to 10 days to avoid crossing GitHub's [rate limits](https://developer.github.com/v3/rate_limit/), but if your project has more than a few contributors and libraries *or* you want it to have access to a private repository, you will need to provide an auth token by calling `.withGitHubToken(token)` on your instance of `Attribouter`.

## Configuration

By default, Attribouter will use the configuration file at [res/xml/attribouter.xml](./attribouter/src/main/res/xml/attribouter.xml). You can either name your configuration file "attribouter.xml" to override the resource, or name it differently and call `.withFile(R.xml.[name])` on your instance of `Attribouter` instead.

The configuration file consists of a single root element, `<about>`, with many child elements that can be placed any amount of times in any order, the same as views in a layout file. These elements, called "wedges" in this library for no apparent reason, are created by Attribouter and added to the page in the order and heirarchy that they are defined in. To create your configuration file, you can either use the [file from the sample project](https://github.com/fennifith/Attribouter/blob/master/./app/src/main/res/xml/about.xml) as a template or use [the documentation](https://jfenn.me/projects/attribouter/wiki) to write your own.

## Proguard

This library uses GSON, which does not behave nicely with proguard as it uses reflection to instantiate classes and initialize variables based on their names. It is recommended to use the [example configuration](https://github.com/google/gson/blob/master/examples/android-proguard-example/proguard.cfg) in GSON's repo to prevent these issues.
