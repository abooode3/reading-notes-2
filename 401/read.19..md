## Using WebSocket to build an interactive web application

- What You Will build
You will build a server that accepts a message that carries a user’s name. In response, the server will push a greeting into a queue to which the client is subscribed.

- Starting with Spring Initializr

- for Gradle: 
 - build.gradle file
 plugins {
	id 'org.springframework.boot' version '2.5.2'
	id 'io.spring.dependency-management' version '1.0.11.RELEASE'
	id 'java'
}

group = 'com.example'
version = '0.0.1-SNAPSHOT'
sourceCompatibility = '1.8'

repositories {
	mavenCentral()
}

dependencies {
	implementation 'org.springframework.boot:spring-boot-starter-websocket'
	testImplementation 'org.springframework.boot:spring-boot-starter-test'
}

test {
	useJUnitPlatform()
}

- Adding Dependencies
* Spring Initializr does not provide everything you need to add it

implementation 'org.webjars:webjars-locator-core'
implementation 'org.webjars:sockjs-client:1.0.2'
implementation 'org.webjars:stomp-websocket:2.3.3'
implementation 'org.webjars:bootstrap:3.3.7'
implementation 'org.webjars:jquery:3.1.1-1'


- Create a Resource Representation Class
* Now that you have set up the project and build system, you can create your STOMP message service.

* The service will accept messages that contain a name in a STOMP message whose body is a JSON object

- Create a Message-handling Controller
* In Spring’s approach to working with STOMP messaging, STOMP messages can be routed to @Controller

- Configure Spring for STOMP messaging

- Create a Browser Client

- Make the Application Executable

- Build an executable JAR

- Test the service
