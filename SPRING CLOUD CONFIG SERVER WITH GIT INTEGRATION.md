# ![spring-git](C:\Users\user\Pictures\spring-git.png)

# SPRING CLOUD CONFIG SERVER WITH GIT INTEGRATION

Config server is where all configurable parameters of microservices are written and maintained. It is more like externalizing properties / resources file out of project codebase to an external service altogether, so that any changes to that property does not necessitate the deployment of service which is using the property. All such property changes will be reflected without redeploying the microservice.

## Requirements

1. Java 1.8

2. Eclipse IDE

3. Spring Cloud

4. Spring Boot

5. Spring Rest

6. GitHub

7. Maven

8. REST Client

## Confiig Server - Server Side Configuration

1. ### Generate the Project Structure

   Start with spring boot initializer portal which is a great starting point for creating any spring boot based application. Here we will choose only Config server starter pom. With this configuration, once we generate the project, one zip file will be downloaded, which we will simply import in eclipse after unzipping.

   ​

![Generate Server Project with Config Server Starter POM](https://howtodoinjava.com/wp-content/uploads/2017/07/server_generation.png)

2. ### Import the Project in Eclipse

   Once you have the zip file from the spring initializer portal, we need to unzp it to a directory we choose to and import it to eclipse as maven project.

   ![Screenshot (99)](C:\Users\user\Pictures\Screenshots\Screenshot (99).png)



3. ### Build in Eclipse

   Run mvn clean install from either command prompt or from eclipse whatever you are comfortable with. In this step, all necessary dependencies will be downloaded from maven repo. Make sure you are trying it from any network where no download restriction is present. Successful build in this step is very much required to proceed to the next steps.

   ![Screenshot (100)](C:\Users\user\Pictures\Screenshots\Screenshot (100).png)



4. ### Add Config Server Annotation

   Now open the Spring Application class that spring already has provided and add the `EnableConfigServer` annotation before the class and build the project once again. With this annotation, this artifact will act like a spring config server.

   ![Screenshot (101)](C:\Users\user\Pictures\Screenshots\Screenshot (101).png)



5. ### Create the Git Repository

   Next very important step is to create a local git repository. It can easily be converted to a remote repository later by configuring it's URL in the properties file. We will place the external property file [configuration], which will be used by the Config server Microservice to provide the external configuration of properties. We need to follow the below steps to create a logical git repository and check in sample properties file.

   1. Create a directory config-server-repo in specific directory.

   2. Create a file `config-server-client.properties` file in the config-server-repo directory and add the message there `msg = Hello World -  this is from config server`.

   3. Create another file `config-server-client-development.properties`file in the config-server-repo directory and add the message there `msg = Hello Worl - this is from config server - Development environment`.

   4. Create another file `config-server-client-production.properties`file in the config-server-repo directory and add the message there `msg = Hello World - this is from config server - Production environment`.

   5. Here we are maintaining same property name for different environment, as we generally maintain properties for different environments like urls, credentials, database details etc. Here the most important point is that we need to append hyphen (-) with the environment name in each property so that config server understands it. Also, we need to name the properties file with the config client service name that we will create after this.

   6. Open Command Prompt from config-server-repo directory and run command `git init`to make that directory as git repository.

   7. Run `git add .`to add everything to this repo.

   8. Then finally we need to commit the properties file by running command `git commit -m "initial commit"`This should check in all the files in the git repository.

      ![Screenshot (102)](C:\Users\user\Pictures\Screenshots\Screenshot (102).png)

   ### 

6. ### Point the git Repo from Config Server

   Create one file called `bootstrap.properties`in the `src\main\resources`directory of `spring-config-server`project and add the below lines:

   ​

   `#Server port`

   `server.port = ``8888`

   ​

   `#Git repo location.`

   `spring.cloud.config.server.git.uri=${USERPROFILE}\\SpringBoot-Workspace\\config-server-repo`


   `#Disable security of the Management endpoint`

   `management.security.enabled=``false` 

Now lets understand those properties

- `server.port` defines the port on which the embedded server will start.
- `spring.cloud.config.server.git.uri` will bind the git location to look for the configuration. Here we are using local git repo but can switched to remote got location by just changing this location.
- `management.security.enabled=false` will disable the spring security on the management endpoints like /env, /refresh etc. This is for development settings, in production security should be enabled.

7. ### Verify Server Side Configuration

   To check the if the Config-server can recognize the properties, first run the config server microservice from command prompt by using the given command from command prompt of the project code base location.

   `java -jar target\spring-config-server-0.0.1-SNAPSHOT.jar`

   Now open browser and check below Urls, it will return JSON output in propertySources section we can see all the properties we have added in the properties. This ensures that config-server is running successfully, it has recognized the git location and it is serving configuration for different environments.

   - http://localhost:8888/config-server-client/development
   - http://localhost:8888/config-server-client/production

   Also, check if any runtime change in the property file is reflected by the server without restart – Do any change in the value of any environment’s property and check-in that file and then run that specific environment’s endpoint, and verify that changed value should be reflected immediately without restarting the server – that is the magic of Spring Config Server.

   To do the git check in, after doing the change and save the file by any text editor, run the command `git add .` and `git commit -m "test"` from config-server-repo directory in the desktop.






## Config Server - Client Side Configuration

