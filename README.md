# Fenix Webapp Archetype

Use this archetype to create installations of [FenixEdu](http://fenixedu.org).

Run: 
```
mvn archetype:generate -DarchetypeGroupId=org.fenixedu -DarchetypeArtifactId=fenix-webapp-archetype -DarchetypeVersion=1.0.0 -DarchetypeRepository=https://fenix-ashes.ist.utl.pt/nexus/content/groups/fenix-ashes-maven-repository
```

This will prompt you for your database credentials, maven information and the version of Fenix you wish to install (Note that due to maven limitations, empty database passwords are not supported).

The generated application will not use a Configuration file, instead relying on defaults. To create a configuration file, run `mvn bennu:generate-configuration`.

First, you need to bootstrap the application. Run `mvn clean package -Pinstall` (If this fails with an OutOfMemoryError, tune your MAVEN_OPTS environment variable).

You now have a fully working Fenix installation! Either deploy the war file in `target/`, or run `mvn tomcat7:run` to start your application.
