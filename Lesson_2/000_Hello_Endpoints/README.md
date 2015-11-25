endpoints-skeleton
==================

A skeleton application for Google Cloud Endpoints in Java.

- [App Engine][1]

- [Java][2]

- [Google Cloud Endpoints][3]
- [Google App Engine Maven plugin][4]


1. Update the value of `application` in `appengine-web.xml` to the app
   ID you have registered in the App Engine admin console and would
   like to use to host your instance of this sample.

1. Add your API method to `src/main/java/com/google/training/helloworld/YourFirstAPI.java`.

1. Optional step: These sub steps are not required but you need this
   if you want to have auth protected methods.

    1. Update the values in `src/main/java/com/google/training/helloworld/Constants.java`
       to reflect the respective client IDs you have registered in the
       [APIs Console][6]. 

    1. You also need to supply the web client ID you have registered
       in the [APIs Console][4] to your client of choice (web, Android,
       iOS).

1. Run the application with `mvn appengine:devserver`, and ensure it's
   running by visiting your local server's api explorer's address (by
   default [localhost:8080/_ah/api/explorer][5].)

1. Get the client library with

   $ mvnappengine:endpoints_get_client_lib

   It will generate a client library jar file under the
   `target/endpoints-client-libs/<api-name>/target` directory of your
   project, as well as install the artifact into your local maven
   repository.

1. Deploy your application to Google App Engine with

   $ mvn appengine:update

[1]: https://developers.google.com/appengine
[2]: http://java.com/en/
[3]: https://developers.google.com/appengine/docs/java/endpoints/
[4]: https://developers.google.com/appengine/docs/java/tools/maven
[5]: https://localhost:8080/_ah/api/explorer
[6]: https://console.developers.google.com/

     1	19:19	java -version
     2	19:19	pwd
     3	19:19	mvn -version
     4	19:19	pwd
     5	19:19	cd ~/git/ud859/
     6	19:19	ls
     7	19:19	cd Lesson_2/
     8	19:19	ls
     9	19:19	cd 000_Hello_Endpoints/
    10	19:19	ls
    11	19:20	~/.m2/repository/com/google/appengine/appengine-java-sdk/1.9.4/appengine-java-sdk/appengine-java-sdk-1.9.4/bin/dev_appserver.sh target/helloworld-1.0-SNAPSHOT.war
    12	19:20	~/.m2/repository/com/google/appengine/appengine-java-sdk/1.9.4/appengine-java-sdk/appengine-java-sdk-1.9.4/bin/dev_appserver.sh target
    13	19:21	~/.m2/repository/com/google/appengine/appengine-java-sdk/1.9.4/appengine-java-sdk/appengine-java-sdk-1.9.4/bin/dev_appserver.sh target/helloworld-1.0-SNAPSHOT.war
    14	19:21	~/.m2/repository/com/google/appengine/appengine-java-sdk/1.9.4/appengine-java-sdk/appengine-java-sdk-1.9.4/bin/dev_appserver.sh target/helloworld-1.0-SNAPSHOT
    15	19:22	~/.m2/repository/com/google/appengine/appengine-java-sdk/1.9.4/appengine-java-sdk/appengine-java-sdk-1.9.4/bin/dev_appserver.sh target/helloworld-1.0-SNAPSHOT
    16	19:22	~/.m2/repository/com/google/appengine/appengine-java-sdk/1.9.4/appengine-java-sdk/appengine-java-sdk-1.9.4/bin/dev_appserver.sh -help
    17	19:23	~/.m2/repository/com/google/appengine/appengine-java-sdk/1.9.4/appengine-java-sdk/appengine-java-sdk-1.9.4/bin/dev_appserver.sh -a 0.0.0.0 target/helloworld-1.0-SNAPSHOT
    18	19:29	pwd
    19	19:29	history
    20	19:30	history | grep mvn
    21	19:30	pwd
    22	19:30	mvn appengin:devserver
    23	19:31	mvn --address=0.0.0.0 appengin:devserver
    24	19:31	pwd
    25	19:31	ls -l
    26	19:31	mvn --address=0.0.0.0 appengine:devserver
    27	19:31	mvn --address=0.0.0.0 appengine:devserver | & more
    28	19:32	ls -l
    29	19:32	vi pom.xml
    30	19:33	mvn clean install
    31	19:33	vi pom.xml
    32	19:33	mvn appengine:devserver
    33	19:34	mvn appengine:devserver | & more
    34	19:35	vi pom.xml
    35	19:37	mvn clean install

[pom.xml] <address>0.0.0.0</address> under
                <artifactId>appengine-maven-plugin</artifactId>
                <configuration>
[INFO] Scanning for projects...
[INFO]                                                                         
[INFO] ------------------------------------------------------------------------
[INFO] Building helloworld 1.0-SNAPSHOT
[INFO] ------------------------------------------------------------------------
[INFO] 
[INFO] >>> appengine-maven-plugin:1.9.4:update (default-cli) > package @ helloworld >>>
[INFO] 
[INFO] --- maven-resources-plugin:2.6:resources (default-resources) @ helloworld ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] skip non existing resourceDirectory /root/git/ud859/Lesson_2/000_Hello_Endpoints/src/main/resources
[INFO] 
[INFO] --- maven-compiler-plugin:3.1:compile (default-compile) @ helloworld ---
[INFO] Nothing to compile - all classes are up to date
[INFO] 
[INFO] --- appengine-maven-plugin:1.9.4:endpoints_get_discovery_doc (default) @ helloworld ---
[INFO] 
[INFO] Google App Engine Java SDK - get endpoints discovery doc...
[INFO] Using Class Name:com.google.training.helloworld.HelloWorldEndpoints
[INFO] Executing endpoints Command=[get-discovery-doc, -cp, /root/git/ud859/Lesson_2/000_Hello_Endpoints/target/helloworld-1.0-SNAPSHOT/WEB-INF/classes:/root/git/ud859/Lesson_2/000_Hello_Endpoints/target/classes:/root/.m2/repository/com/google/appengine/appengine-api-1.0-sdk/1.9.4/appengine-api-1.0-sdk-1.9.4.jar:/root/.m2/repository/com/google/appengine/appengine-endpoints/1.9.4/appengine-endpoints-1.9.4.jar:/root/.m2/repository/javax/inject/javax.inject/1/javax.inject-1.jar, -o, /root/git/ud859/Lesson_2/000_Hello_Endpoints/target/generated-sources/appengine-endpoints/WEB-INF, -w, /root/git/ud859/Lesson_2/000_Hello_Endpoints/target/generated-sources/appengine-endpoints, -f, rest, com.google.training.helloworld.HelloWorldEndpoints]
API Discovery Document written to /root/git/ud859/Lesson_2/000_Hello_Endpoints/target/generated-sources/appengine-endpoints/WEB-INF/helloworldendpoints-v1-rest.discovery
[INFO] Using Class Name:com.google.training.helloworld.HelloWorldEndpoints
[INFO] Executing endpoints Command=[get-discovery-doc, -cp, /root/git/ud859/Lesson_2/000_Hello_Endpoints/target/helloworld-1.0-SNAPSHOT/WEB-INF/classes:/root/git/ud859/Lesson_2/000_Hello_Endpoints/target/classes:/root/.m2/repository/com/google/appengine/appengine-api-1.0-sdk/1.9.4/appengine-api-1.0-sdk-1.9.4.jar:/root/.m2/repository/com/google/appengine/appengine-endpoints/1.9.4/appengine-endpoints-1.9.4.jar:/root/.m2/repository/javax/inject/javax.inject/1/javax.inject-1.jar, -o, /root/git/ud859/Lesson_2/000_Hello_Endpoints/target/generated-sources/appengine-endpoints/WEB-INF, -w, /root/git/ud859/Lesson_2/000_Hello_Endpoints/target/generated-sources/appengine-endpoints, -f, rpc, com.google.training.helloworld.HelloWorldEndpoints]
API Discovery Document written to /root/git/ud859/Lesson_2/000_Hello_Endpoints/target/generated-sources/appengine-endpoints/WEB-INF/helloworldendpoints-v1-rpc.discovery
[INFO] Endpoints discovery doc generation done.
[INFO] 
[INFO] --- maven-resources-plugin:2.6:testResources (default-testResources) @ helloworld ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] skip non existing resourceDirectory /root/git/ud859/Lesson_2/000_Hello_Endpoints/src/test/resources
[INFO] 
[INFO] --- maven-compiler-plugin:3.1:testCompile (default-testCompile) @ helloworld ---
[INFO] No sources to compile
[INFO] 
[INFO] --- maven-surefire-plugin:2.12.4:test (default-test) @ helloworld ---
[INFO] No tests to run.
[INFO] 
[INFO] --- maven-war-plugin:2.4:war (default-war) @ helloworld ---
[INFO] Packaging webapp
[INFO] Assembling webapp [helloworld] in [/root/git/ud859/Lesson_2/000_Hello_Endpoints/target/helloworld-1.0-SNAPSHOT]
[INFO] Processing war project
[INFO] Copying webapp webResources [/root/git/ud859/Lesson_2/000_Hello_Endpoints/target/generated-sources/appengine-endpoints] to [/root/git/ud859/Lesson_2/000_Hello_Endpoints/target/helloworld-1.0-SNAPSHOT]
[INFO] Copying webapp resources [/root/git/ud859/Lesson_2/000_Hello_Endpoints/src/main/webapp]
[INFO] Webapp assembled in [290 msecs]
[INFO] Building war: /root/git/ud859/Lesson_2/000_Hello_Endpoints/target/helloworld-1.0-SNAPSHOT.war
[INFO] 
[INFO] <<< appengine-maven-plugin:1.9.4:update (default-cli) < package @ helloworld <<<
[INFO] 
[INFO] --- appengine-maven-plugin:1.9.4:update (default-cli) @ helloworld ---
[INFO] 
[INFO] Google App Engine Java SDK - Updating Application
[INFO] 
[INFO] Retrieving Google App Engine Java SDK from Maven
[INFO] Updating Google App Engine Application
Please open the following URL in your browser:
  https://accounts.google.com/o/oauth2/auth?access_type=offline&approval_prompt=force&client_id=550516889912.apps.googleusercontent.com&redirect_uri=urn:ietf:wg:oauth:2.0:oob&response_type=code&scope=https://www.googleapis.com/auth/appengine.admin
Please enter code: 