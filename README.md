# 5 Ways to Boost Android App's Performance.

## 1. R8/ Prograud
- To protect from `Reverse Engineering`.
- Reduced APK/Bundle size. Basically, this renames all of your classes to smaller names and it removes the unused classes, functions and res/images.

> ## How to enable..?

```
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

## 2.  Android Studio Profiler ( Inside Android Studio)

- Provide insides on ` Battery Consumption ` , ` Network Consumption `, ` CPU/ RAM consumption `

 <img width="713" alt="image" src="https://github.com/Brindha-m/Boost_Android_Performance/assets/72887609/fa486112-f399-4896-bf61-f5248acd0528">



## 3. Caching Data

- Especially for images use caching libraries like `coil, picasso, glide`. Also whenever using persistent storage - RoomDB
- Main Moto is to fastly access our data.

## 4. Memory Leakage

- Mainly due ` GC (Garbage Collector) ` does'nt collect the unused objects. It should always get the unused/unwanted objects and should ` remove the memory space `, if this is not happening properly then it may lead to memory leaks.

> ## How to Control..?

- Make use of an App called `LEAK CANARY`
  
  ```
  dependencies {
    // debugImplementation because LeakCanary should only run in debug builds.
    debugImplementation 'com.squareup.leakcanary:leakcanary-android:2.12'
  }

  ```

## 5. Optimize Networking - to save phone's battery

- Synchronize all the request and send it to the server. Make use of `Work Manager`.
