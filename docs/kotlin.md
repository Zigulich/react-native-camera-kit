# Add Kotlin Support for Android

1. Open and edit android/build.gradle

Add the `kotlinVersion` to `buildscript.ext`

```
buildscript {
  ext {
        ...
        kotlinVersion = '1.7.20'
  }
```

Add `google()` to the `buildscript.repositories` and `allprojects.repositories`

```
buildscript {
    repositories {
        ...
        google()
    }
}

allprojects {
    repositories {
        ...
        google()
    }
}
```

Add the Kotlin classpath to `buildscript.dependencies`

```
dependencies {
    ...
    classpath("com.android.tools.build:gradle:7.0.2") // or recent
    classpath("org.jetbrains.kotlin:kotlin-gradle-plugin:$kotlinVersion")
}
```

2. Open and edit android/app/build.gradle

Add Kotlin imports

```
apply plugin: "kotlin-android"
apply plugin: "kotlin-android-extensions"
```