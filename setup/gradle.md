# Gradle

 To start you need to add the dependency to your `build.gradle`.

```groovy
repositories {
    mavenCentral()
}

dependencies {
    compile "me.mattstudios.utils:matt-framework:{version}" // Replace version here 
}
```

 In order to include the framework in your project, you need to add `shadowJar` plugin `build.gradle`.  
 Replace `[YOUR PACKAGE]` with your plugin's package, for example `me.myplugin.plugin`.

```groovy
apply plugin: 'com.github.johnrengelman.shadow'

shadowJar {
   relocate 'me.mattstudios.mf', '[YOU PACKAGE].mf'
}
```



