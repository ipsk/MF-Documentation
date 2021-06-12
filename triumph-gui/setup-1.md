---
description: This is how you add the lib to your project.
---

# Setup

### Version

Make sure to replace `{version}` with the latest version.  
Latest version: `3.0.0`

{% tabs %}
{% tab title="Gradle" %}
You need to add the dependency to your `build.gradle`.

```groovy
repositories {
    maven { url = "https://repo.mattstudios.me/artifactory/public/" }
}

dependencies {
    implementation "dev.triumphteam:triumph-gui:{version}" // Replace version here 
}
```

 In order to include the lib in your project, you need to add `shadowJar` plugin `build.gradle`.  
 Replace `[YOUR PACKAGE]`with your plugin's package, for example `me.myplugin.plugin`.

```groovy
plugins {
    id "com.github.johnrengelman.shadow" version "7.0.0"
}

shadowJar {
   relocate("dev.triumphteam.gui", "[YOUR PACKAGE].gui")
}
```
{% endtab %}

{% tab title="Maven" %}
You need to add the dependency to your pom.xml.

```markup
<repositories>
    <repository>
        <id>repo</id>
        <url>https://repo.mattstudios.me/artifactory/public/</url>
    </repository>
</repositories>

<dependency>
    <groupId>dev.triumphteam</groupId>
    <artifactId>triumph-gui</artifactId>
    <version>{version}</version> <!-- replace version here -->
</dependency>
```

 In order to include the framework in your project, you need to add the following to your `pom.xml`, in the plugins section.  
 Replace `[YOUR PACKAGE]`with your plugin's package, for example `me.myplugin.plugin`.

```markup
<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-shade-plugin</artifactId>
    <version>3.1.1</version>
    <configuration>
        <relocations>
            <relocation>
                <pattern>dev.triumphteam.gui</pattern>
                <shadedPattern>[YOUR PACKAGE].gui</shadedPattern> <!-- Replace package here here -->
            </relocation>
        </relocations>
    </configuration>
    <executions>
        <execution>
            <phase>package</phase>
            <goals>
                <goal>shade</goal>
            </goals>
        </execution>
    </executions>
</plugin>
```
{% endtab %}
{% endtabs %}

