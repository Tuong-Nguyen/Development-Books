# Introduction

\[Robolectric\]\([http://robolectric.org/](http://robolectric.org/)\) is a unit test framework that de-fangs the Android SDK jar so you can test-drive the development of your Android app.

The tests can be run on JVM not Emulator so they are faster.

# Set up - Add Robolectric tests

Add Robolectric library into `build.gradle`

```groovy
testCompile "org.robolectric:robolectric:3.3.2"
```

Add a test:

```java
@RunWith(RobolectricTestRunner.class)
@Config(constants=BuildConfig.class)
public class SandwichTest {
}
```

## Configuring Robolectric [http://robolectric.org/configuring/](http://robolectric.org/configuring/)

There are configurables which can be set for Robolectric:

* SDK level
* Application class
* Resource and Asset Paths
* Quantifiers

They can be configured using **@Configure** annotation or **robolectric.properties** file

## Driving Activity Lifecycle [http://robolectric.org/activity-lifecycle/](http://robolectric.org/activity-lifecycle/)

Robolectric allows us to drive the activity lifecycle. Therefore, be noticed to call appropriate methods to move activity to expecting state.



