# android-widget
This is a SDK for use Olivia widget into your Android App.

Olivia Widget for Android supports API 19 and above.

## Installation
Install Olivia Widget with gradle:

Add the following dependency to your app's `build.gradle` file:
```groovy
dependencies {
    implement 'https://github.com/OliviaAI/android-widget'alterar
 }
```
## ProGuard

If you are using ProGuard, add the following rules:

```
-keep class ai.olivia.lib.** { *; }
```
You might also need to add rules for OkHttp, Okio and Retrofit which are dependencies used in this library.


## Permissions

We include the [INTERNET](http://developer.android.com/reference/android/Manifest.permission.html#INTERNET) permission by default as we need it to make network requests:

```xml
<uses-permission android:name="android.permission.INTERNET"/>
```

## Dependency graph

Here is our complete dependency graph:

### olivia-sdk-base
```
com.android.support:design:27.1.1
com.android.support:appcompat-v7:28.0.0-beta01
com.android.support.constraint:constraint-layout:1.1.2
junit:junit:4.12
com.android.support.test:runner:1.0.2
com.android.support.test.espresso:espresso-core:3.0.2
com.android.support:recyclerview-v7:28.0.0-beta01
com.android.support:design:28.0.0-beta01

com.squareup.retrofit2:retrofit:2.4.0
com.squareup.retrofit2:converter-gson:2.3.0
ru.terrakok.cicerone:cicerone:2.1.0
org.jetbrains.anko:anko:$anko_version
com.github.bumptech.glide:glide:4.8.0
com.github.bumptech.glide:compiler:4.8.0
jp.wasabeef:glide-transformations:3.3.0
com.squareup.okhttp3:okhttp:3.11.0
com.eyalbira.loadingdots:loading-dots:1.0.2
```
## Usage


To declare your userID:
```groovy
import ai.olivia.lib.Singleton.Olivia

Olivia.init(context)
Olivia.setUser("user","password")
```

To open the Chat Screen:

```groovy
import ai.olivia.lib.view.activity.ChatActivity

val i = Intent(this@MainActivity, ChatActivity::class.java)
startActivity(i)

```

To open the Chat Screen with notification params:

```groovy
import ai.olivia.lib.view.activity.ChatActivity

val i = Intent(this@MainActivity, ChatActivity::class.java)
i.putExtra("OliviaNotification", "stringFromNotification")
startActivity(i)

```

To customize the Chat Screen
```groovy
Olivia.appBarColor = Color.parseColor("#CCCCCC")
Olivia.background = Color.parseColor("#B0E58A")

Olivia.userBubbleColor = Color.parseColor("#B76FB1")
Olivia.userTextColor = Color.parseColor("#FFB99A")

Olivia.oliviaBubbleColor = Color.parseColor("#394F2A")
Olivia.oliviaTextColor = Color.parseColor("#CCCCCC")

Olivia.fontSize = 18.0f

Olivia.fontFamily = Typeface.SERIF
```

To declare Open App Event:
```groovy
import ai.olivia.lib.Singleton.Olivia
Olivia.init(this)
Olivia.openApp()
```

To declare Enable Notification Event:
```groovy
import ai.olivia.lib.Singleton.Olivia
Olivia.init(this)
Olivia.enabledNotification()
```


To declare Disable Notification Event:
```groovy
import ai.olivia.lib.Singleton.Olivia
Olivia.init(this)
Olivia.disableNotification()
```
