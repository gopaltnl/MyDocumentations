
# Espresso Testing In Android

spresso is an open source android user interface (UI) testing framework developed by Google. The term Espresso is of Italian origin, meaning Coffee. Espresso is a simple, efficient and flexible testing framework. This tutorial walks you through the basics of Espresso framework, how to setup Espresso framework in a project, work flow of the framework and finding, automating & asserting user interface components in the testing environment with simple android application.
In general, mobile automation testing is a difficult and challenging task. Android availability for different devices and platforms makes it things tedious for mobile automation testing. To make it easier, Google took on the challenge and developed Espresso framework. It provides a very simple, consistent and flexible API to automate and test the user interfaces in an android application. Espresso tests can be written in both Java and Kotlin, a modern programming language to develop android application.

The Espresso API is simple and easy to learn. You can easily perform Android UI tests without the complexity of multi-threaded testing. Google Drive, Maps and some other applications are currently using Espresso.

## Features of Espresso

Some the salient features supported by Espresso are as follow,

* Very simple API and so, easy to learn.

* Highly scalable and flexible.

* Provides separate module to test Android WebView component.

* Provides separate module to validate as well as mock Android Intents.

* Provides automatic synchronization between your application and tests.

## Advantages of Espresso

Let us now what the benefits of Espresso are.

* Backward compatibility

* Easy to setup.

* Highly stable test cycle.

* Supports testing activities outside application as well.

* Supports JUnit4

* UI automation suitable for writing black box tests.

let us understand how to install espresso framework, configure it to write espresso tests and execute it in our android application.

## Prerequisites

Espresso is a user interface-testing framework for testing android application developed in Java / Kotlin language using Android SDK. Therefore, espresso’s only requirement is to develop the application using Android SDK in either Java or Kotlin and it is advised to have the latest Android Studio.

The list of items to be configured properly before we start working in espresso framework is as follows −

* Install latest Java JDK and configure JAVA_HOME environment variable.

* Install latest Android Studio (version 3.2. or higher).

* Install latest Android SDK using SDK Manager and configure ANDROID_HOME environment variable.

* Install latest Gradle Build Tool and configure GRADLE_HOME environment variable.

## Configure EspressoTesting Framework

Initially, espresso testing framework is provided as part of the Android Support library. Later, the Android team provides a new Android library, AndroidX and moves the latest espresso testing framework development into the library. Latest development (Android 9.0, API level 28 or higher) of espresso testing framework will be done in AndroidX library.

Including espresso testing framework in a project is as simple as setting the espresso testing framework as a dependency in the application gradle file, app/build.gradle. The complete configuration is as follow,

Using Android support library,

```
android {
   defaultConfig {
      testInstrumentationRunner "android.support.test.runner.AndroidJUnitRunner"
   }
}
dependencies {
   testImplementation 'junit:junit:4.12'
   androidTestImplementation 'com.android.support.test:runner:1.0.2'
   androidTestImplementation 'com.android.support.test.espresso:espressocore:3.0.2'
}
```
Using AndroidX library,

```
android {
   defaultConfig {
      testInstrumentationRunner "androidx.test.runner.AndroidJUnitRunner"
   }
}
dependencies {
   testImplementation 'junit:junit:4.12'
   androidTestImplementation 'com.androidx.test:runner:1.0.2'
   androidTestImplementation 'com.androidx.espresso:espresso-core:3.0.2'
}
```
# 1. The Espresso test framework

Espresso has basically three components:

ViewMatchers - allows to find view in the current view hierarchy

ViewActions - allows to perform actions on the views

ViewAssertions - allows to assert state of a view

The case construct for Espresso tests is the following:

## Base Espresso Test

```
onView(ViewMatcher)  1     
 .perform(ViewAction) 2    
   .check(ViewAssertion); 3
```
1.Finds the view
2.Performs an action on the view
3.Validates a assertioin

The following code demonstrates the usage of the Espresso test framework.
```
import static android.support.test.espresso.Espresso.onView;
import static android.support.test.espresso.action.ViewActions.click;
import static android.support.test.espresso.assertion.ViewAssertions.matches;
import static android.support.test.espresso.matcher.ViewMatchers.isDisplayed;
import static android.support.test.espresso.matcher.ViewMatchers.withId;

// image more code here...

// test statement
onView(withId(R.id.my_view))            // withId(R.id.my_view) is a ViewMatcher
        .perform(click())               // click() is a ViewAction
        .check(matches(isDisplayed())); // matches(isDisplayed()) is a ViewAssertion

// new test
onView(withId(R.id.greet_button))
.perform(click())
.check(matches(not(isEnabled()));

```
# 2. Making Espresso available
## 2.1. Installation
Use the Android SDK manager to install the Android Support Repository.

```

```
