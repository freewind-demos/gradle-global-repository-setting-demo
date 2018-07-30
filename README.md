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

But it's a pity that `repositories` in `buildscript` is still not configurable globally, that means, it's NOT working to put following the `~/.gradle/init.gradle`:

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
