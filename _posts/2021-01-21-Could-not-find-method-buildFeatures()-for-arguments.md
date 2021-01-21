---
layout: post
title: "Use Android View Binding in old android gradle build tool 3.6 "
comments: true
description: "Use Android View Binding in old android gradle build tool 3.6"
keywords: "View Binding"
---

### Use Android buildFeatures in old android gradle build tool 3.6

If you want to use **buildFeatures** like View Binding in Android studio project that using outdate gradle build tool like version 3.6 and follow 
Android Document Website add the following code to build gradle file:

```gradle
    android {
    ...
        buildFeatures {
            viewBinding true
        }
    }
```
Android Studio will not compile and throw following error:


>Could not find method buildFeatures() for arguments ... on object of type com.android.build.gradle.internal.dsl.BaseAppModuleExtension

You don't want to risk updating Gradle build tool. Just change to use the following code. 
```
// Available in Android Gradle Plugin 3.6.0
    android {
        viewBinding {
            enabled = true
        }
    }
```

Rebuild your project, and the error will go away.

#### Cheers! 
