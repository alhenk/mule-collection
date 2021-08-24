# uc-invoke-java

### Invoke Java methods

- Invoke class method from a jar in pom dependencies
- Invoke static method from a jar in pom dependencies
- Invoke class method from the project source folder

### External jar file
#### Build a jar file
```
package com.mycompany.usecase.javainvoke;

public class Utils {
    public Utils(){

    }
    public String greet(String name){
        return "Hi there, " + name + "!";
    }

    public static String goodbye(String name){
        return "Goodbye " + name + "!";
    }
}
```
run "install" for publishing it in a local .m2 maven repository

#### Add the dependency to mule project pom file

```
<dependency>
   <groupId>com.mycompany.usecase</groupId>
   <artifactId>javainvoke</artifactId>
   <version>1.0</version>
</dependency>
```

- For class methods use Java "New" component and choose a constructor

- For static methods use "import java"

```
%dw 2.0
output application/json
import java!com::mycompany::usecase::javainvoke::Utils
---
```


