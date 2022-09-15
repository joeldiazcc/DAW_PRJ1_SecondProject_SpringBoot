<p align="center"><a href="https://spring.io/projects/spring-boot" target="_blank"><img src="https://spring.io/images/spring-logo-9146a4d3298760c2e7e49595184e1975.svg" width="400"></a></p>

# First Week Project 

The project aims to do a Quick Start from SpringBoot
A simple Hello World


### Organization 📋

-  joeldiazcc, lcastienc -> Do the QuickStart from Spring Tool for Eclipse.

-  joeldiazcc -> Upload the project to GitHub and Readme.


## Documentation 📄

### Step 1: Start a new Spring Boot project
Use start.spring.io to create a “web” project. In the “Dependencies” dialog search for and add the “web” dependency as shown in the screenshot. Hit the “Generate” button, download the zip, and unpack it into a folder on your computer.

<img src="https://spring.io/images/quick-img-1-dark-fa196953fc04a4d6ab1133c05a622787.png">


### Step 2: Add your code
Open up the project in your IDE and locate the DemoApplication.java file in the src/main/java/com/example/demo folder. Now change the contents of the file by adding the extra method and annotations shown in the code below. You can copy and paste the code or just type it.
```
package com.example.demo;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RequestParam;
import org.springframework.web.bind.annotation.RestController;

@SpringBootApplication
@RestController
public class DemoApplication {

public static void main(String[] args) {
SpringApplication.run(DemoApplication.class, args);
}

@GetMapping("/hello")
public String hello(@RequestParam(value = "name", defaultValue = "World") String name) {
return String.format("Hello %s!", name);
}
}
```
This is all the code required to create a simple “Hello World” web service in Spring Boot.

The hello() method we’ve added is designed to take a String parameter called name, and then combine this parameter with the word "Hello" in the code. This means that if you set your name to “Amy” in the request, the response would be “Hello Amy”.

The @RestController annotation tells Spring that this code describes an endpoint that should be made available over the web. The @GetMapping(“/hello”) tells Spring to use our hello() method to answer requests that get sent to the http://localhost:8080/hello address. Finally, the @RequestParam is telling Spring to expect a name value in the request, but if it’s not there, it will use the word “World” by default.

### Step 3: Try it
Let’s build and run the program. Open a command line (or terminal) and navigate to the folder where you have the project files. We can build and run the application by issuing the following command:

MacOS/Linux:

```./mvnw spring-boot:run```

Windows:


```mvnw spring-boot:run```

You should see some output that looks very similar to this:
<img src="https://spring.io/images/quick-img2-ac5ae88c60ffaa062234a580f9f1abc3.png">

The last couple of lines here tell us that Spring has started. Spring Boot’s embedded Apache Tomcat server is acting as a webserver and is listening for requests on localhost port 8080. Open your browser and in the address bar at the top enter http://localhost:8080/hello. You should get a nice friendly response like this:

<img src="https://spring.io/images/quick-img3-afa0a1fe446db8e3c8c7a8d9ca532d23.png">

## Repository Authors✒️

-   Joel Felipe Díaz Carissimi - [joeldiazcc](https://github.com/joeldiazcc)

-   Luis Andres Castillo Ensinas - [lcastienc](https://github.com/lcastienc)

## License

The Spring Boot is an open-source micro framework software licensed under the [MIT license](https://opensource.org/licenses/MIT).
Documentation from https://spring.io/quickstart

