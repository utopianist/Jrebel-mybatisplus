# jrebel-mybatisplus

A hook plugin for Support MybatisPlus that reloads modified SQL maps.

([中文](README.md)|English)

# Preconditions

1. `mybatis-plus:3.1.1+`

2. IDEA Run/Debug Configurations
 
   > On 'Update' actions: Update classes and resources
 
   > On frame deactivation:  Update classes and resources

# How to use 

## Use IDEA plugin

You can download the plugin from jetbrains plugins market [jrebel-mybatisplus-extension](https://plugins.jetbrains.com/plugin/12682-jrebel-mybatisplus-extension).

## Local build

Running the web app with the custom plugin
Compile the JRebel plugin like a regular maven project: `mvn -f jr-mybatisplus/pom.xml clean package`. This will produce a plugin jar in jr-mybatisplus/target/jr-mybatisplus.jar. To enable the plugin, pass the plugin’s path to JRebel using a JVM argument: `-Drebel.plugins=/path/to/jr-mybatisplus.jar`.


Running from the IDE
Compile the sample application and the sample plugin using mvn clean package. Configure your favourite web server with the JVM argument -Drebel.plugins=/path/to/jr-mybatisplus.jar, start it with JRebel and deploy the sample application.


Running from the command line
Compile the sample application and the sample plugin using `mvn clean package`. Attach the JRebel agent as usual, but also add the path to the sample plugin:

Linux and Mac OS:
```
export MAVEN_OPTS="<agentpath argument> -Drebel.plugins=/path/to/jr-mybatisplus.jar"
mvn -f demo-application/pom.xml jetty:run
```
Windows:
```
set MAVEN_OPTS="<agentpath argument> -Drebel.plugins=/path/to/jr-mybatisplus.jar"
mvn -f demo-application\pom.xml jetty:run
```
Check that the plugin works:

Modify your `Mybatis mapper` xml file. The “Reloading SQL maps” message should appear in the console at the start of the next request.



# Reference

[Custom JRebel plugins](http://manuals.zeroturnaround.com/jrebel/advanced/custom.html#jrebelcustom)

[Getting Started with Javassist](http://www.javassist.org/tutorial/tutorial.html)

