plugins {
    id("com.android.application")
}

android {
    namespace = "Nepmods.Tester"
    compileSdk = 36

    defaultConfig {
        applicationId = "Nepmods.Tester"
        minSdk = 21
        targetSdk = 36
        versionCode = 35
        versionName = "V3"

        ndk {
            abiFilters += listOf("armeabi-v7a", "arm64-v8a", "x86_64", "x86")
        }
    }

    compileOptions {
        sourceCompatibility = JavaVersion.VERSION_17
        targetCompatibility = JavaVersion.VERSION_17
    }

    signingConfigs {
        getByName("debug") {
            storeFile = file("HunMod.jks")
            storePassword = "HunMod"
            keyAlias = "HunMod"
            keyPassword = "HunMod"
        }
        create("release") {
            storeFile = file("HunMod.jks")
            storePassword = "HunMod"
            keyAlias = "HunMod"
            keyPassword = "HunMod"
        }
    }

    buildTypes {
        getByName("release") {
            isMinifyEnabled = false
            proguardFiles(
                getDefaultProguardFile("proguard-android-optimize.txt"),
                "proguard-rules.pro"
            )
            signingConfig = signingConfigs.getByName("release")
            isDebuggable = false
        }
        getByName("debug") {
            isMinifyEnabled = false
            proguardFiles(
                getDefaultProguardFile("proguard-android-optimize.txt"),
                "proguard-rules.pro"
            )
            signingConfig = signingConfigs.getByName("debug")
            isDebuggable = true
        }
    }

    externalNativeBuild {
        ndkBuild {
            path = file("src/main/jni/Android.mk")
        }
    }
}

dependencies {
    implementation(fileTree(mapOf("dir" to "libs", "include" to listOf("*.jar"))))
}
