# Simple-SMS-Sender-Receiver
Simple android app for sending and receiving SMS messages

This is a basic android app that allows you to send SMS messages to a (currently hardcoded) phone number, and received messages are displayed in a textView.

source : https://github.com/cdoyle45/Simple-SMS-Sender-Receiver

# Fix build error

log error:

```shell
Execution failed for task ':app:checkDebugAarMetadata'.
> Could not resolve all files for configuration ':app:debugRuntimeClasspath'.
   > Could not find com.android.support:appcompat-v7:21.0.3.
     Searched in the following locations:
       - https://jcenter.bintray.com/com/android/support/appcompat-v7/21.0.3/appcompat-v7-21.0.3.pom
     If the artifact you are trying to retrieve can be found in the repository but without metadata in 'Maven POM' format, you need to adjust the 'metadataSources { ... }' of the repository declaration.
     Required by:
         project :app
```

add to file [build.gradle](build.gradle), to both `buildscript` and `allprojects`

```java
        jcenter()
        google()
        maven {
            url "https://maven.google.com"
        }
```