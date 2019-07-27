ConfigManager is a library for Bukkit plugins to simplify the use of multiple configuration files in one plugin.
This code was originally created by **foodyling** and the original post can be found [here](https://bukkit.org/threads/configuration-manager.157660/). 
I updated it for use in 1.12+.

[![Build Status](https://travis-ci.org/mattboy9921/ConfigManager.svg?branch=master)](https://travis-ci.org/mattboy9921/ConfigManager)

**To add this library to your plugin with Maven**

Add the following to your `pom.xml`:

```xml
<repository>
    <id>configmanager-repo</id>
    <url>http://repo.mattlabs.net/repository/maven-public/</url>
</repository>

<dependency>
    <groupId>net.mattlabs.configmanager</groupId>
    <artifactId>ConfigManager</artifactId>
    <version>1.1.0</version>
</dependency>
```