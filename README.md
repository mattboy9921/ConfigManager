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

You will also need to shade the library into your plugin `.jar` file:

```xml
<build>
    <plugins>
        <plugin>
            <version>3.7.0</version>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-compiler-plugin</artifactId>
            <configuration>
                <source>1.8</source>
                <target>1.8</target>
                <compilerArgs>
                    <arg>-parameters</arg>
                </compilerArgs>
            </configuration>
        </plugin>
        <plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-shade-plugin</artifactId>
            <version>3.1.1</version>
            <configuration>
                <dependencyReducedPomLocation>${project.build.directory}/dependency-reduced-pom.xml</dependencyReducedPomLocation>
                <relocations>
                    <relocation>
                        <pattern>net.mattlabs.configmanager</pattern>
                        <shadedPattern>[YOUR PLUGIN PACKAGE].configmanager</shadedPattern> <!-- Replace this -->
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
    </plugins>
</build>
```

Replace `[YOUR PLUGIN PACKAGE]` with a package to your plugin so that SkipNight is relocated to it.