# android_common_script
Android通用脚本

### 版本管理
#### 使用versions.gradle进行版本管理
```
apply from: "https://raw.githubusercontent.com/nicainci/android_common_script/master/versions.gradle"

// rootProject.ext中有版本管理参数
// 例如：
android {
    compileSdkVersion rootProject.ext.compileSdkVersion

    defaultConfig {
        minSdkVersion rootProject.ext.minSdkVersion
        targetSdkVersion rootProject.ext.targetSdkVersion
    }
}

dependencies {
    implementation rootProject.ext.deps.support.app_compat
    implementation rootProject.ext.deps.support.design
    implementation rootProject.ext.deps.support.constraint

    implementation rootProject.ext.deps.butterknife
    annotationProcessor rootProject.ext.deps.butterknife_compiler

    implementation rootProject.ext.deps.arouter
    annotationProcessor rootProject.ext.deps.arouter_compiler
    
    implementation 其他库...
}
```

#### application使用simple_application.gradle
```
// 由于使用到了butterknife 所以记得添加
// classpath 'com.jakewharton:butterknife-gradle-plugin:8.5.1'

apply from: "https://raw.githubusercontent.com/nicainci/android_common_script/master/simple_application.gradle"

android {
    defaultConfig {
        applicationId "包名"
    }
}

dependencies {
    implementation 其他库...
}
```

#### library使用base_library.gradle
```
// 由于使用到了butterknife 所以记得添加
// classpath 'com.jakewharton:butterknife-gradle-plugin:8.5.1'

apply from: "https://raw.githubusercontent.com/nicainci/android_common_script/master/base_library.gradle"

dependencies {
    implementation 其他库...
}
```

