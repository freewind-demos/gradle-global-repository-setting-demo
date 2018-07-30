Gradle Global Repository Setting Demo
=====================================

Create `~/.gradle/init.gradle` with following content:

```
allprojects {
    repositories {
        mavenLocal()
        maven { url 'http://maven.aliyun.com/nexus/content/groups/public/' }
        maven { url 'http://maven.aliyun.com/nexus/content/repositories/jcenter' }
        jcenter()
    }
}
```

Try in current project:

```
./gradlew compileJava
```

You can see it should succeed, even if there is no `repositories` defined in the `build.gradle` file.

Notice
------

It's a pity that `repositories` in `buildscript` is still not configurable globally, that means, it's NOT working to put following the `~/.gradle/init.gradle`:

```
buildscript {
    repositories {
        mavenLocal()
        maven { url 'http://maven.aliyun.com/nexus/content/groups/public/' }
        maven { url 'http://maven.aliyun.com/nexus/content/repositories/jcenter' }
        jcenter()
    }
}
```
