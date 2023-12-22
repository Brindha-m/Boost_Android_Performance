# Ways to Boost Android App's Performance.

## 1. R8/ Prograud
- To protect from `Reverse Engineering`.
- Reduced APK/Bundle size. Basically, this renames all of your classes to smaller names and it removes the unused classes, functions and res/images.

> ## How to enable..?

```kotlin

  buildTypes {
        release {
            isShrinkResources = true
            isMinifyEnabled = true
            proguardFiles(
                getDefaultProguardFile("proguard-android-optimize.txt"),
                "proguard-rules.pro"
            )
        }
    }
```

-----------------


## 2.  Android Studio Profiler ( Inside Android Studio)

- ### View -> Tools Window -> App Profiler

- Provide insights on ` Network Consumption `, ` CPU/ RAM consumption `.

 <img alt="image" src="https://github.com/Brindha-m/Boost_Android_Performance/assets/72887609/fa486112-f399-4896-bf61-f5248acd0528">

  ![image](https://github.com/Brindha-m/Boost_Android_Performance/assets/72887609/46bc8a45-e3f5-4d8f-9301-6b0a35941cb6)


-----------------

## 3. Caching Data

- Especially for images use caching libraries like `coil, picasso, glide`. Also whenever using persistent storage - RoomDB
- Main Moto is to fastly access our data.

-----------------

## 4. Memory Leakage

> ### “A small leak will sink a great ship.”

- Mainly due ` GC (Garbage Collector) ` does'nt collect the unused objects. It should always get the unused/unwanted objects and should ` remove the memory space `, if this is not happening properly then it may lead to memory leaks.

> ## How to Control..?

- Make use of an App called `LEAK CANARY`
  
```kotlin
  dependencies {
    // debugImplementation because LeakCanary should only run in debug builds.
    debugImplementation 'com.squareup.leakcanary:leakcanary-android:2.12'
  }

 ```


-----------------

## 5. Use .svg / .xml for  image drawables

-  The big difference in solving the image size problem by compressing lossless images the solution is to use **Vector Graphics such as SVG images** or use WebP.

-----------------

## 6. Configure your gradle.properties to increase your build speed.

Long build times have always been a problem in the developer’s life.

```kotlin

  org.gradle.daemon=true
  org.gradle.parallel=true
  org.gradle.configureondemand=true
  android.enableBuildCache=true
  org.gradle.jvmargs=-Xmx3072m -XX:MaxPermSize=512m -XX:+HeapDumpOnOutOfMemoryError -Dfile.encoding=UTF-8
  org.gradle.caching= true
  android.useAndroidX=true
  android.enableJetifier=true
  kapt.incremental.apt=true
  kapt.use.worker.api=true

```


-----------------

## 7. Try to reduce the use of small third party libraries

 - Never add whole third party library if it’s possible for you to extract specific methods or small no. of classes for your functionality.

-----------------

## 8. Optimize Networking - to save phone's battery

- Synchronize all the request and send it to the server. Make use of `Work Manager`.

-----------------
  

## 9. Lint Tool 

 - The lint tool helps find poorly structured code that can impact the reliability and efficiency of your Android apps.

![image](https://github.com/Brindha-m/Boost_Android_Performance/assets/72887609/aa604384-05c2-4867-afb2-3ea57a442870)

![image](https://github.com/Brindha-m/Boost_Android_Performance/assets/72887609/46aadab0-bc35-4139-b3bd-94cc1e3a446c)
![image](https://github.com/Brindha-m/Boost_Android_Performance/assets/72887609/133f4c70-d1d2-4110-bf97-428443a3b164)

<img alt="image" src="https://github.com/Brindha-m/Boost_Android_Performance/assets/72887609/b74e1648-3478-492c-a729-fc455f492239">
<img alt="image" src="https://github.com/Brindha-m/Boost_Android_Performance/assets/72887609/0b41197d-d8a0-4010-9114-bd885fe2dc96">
