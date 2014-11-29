soi-toolkit.github.io
=====================

GitHub Pages

# Performing a release

For details see [soi-toolkit v1 Release Handling](https://code.google.com/p/soi-toolkit/wiki/DG_ReleaseHandling).

* Merge develop to master... (using release branch in between?)
* Manually update the soi-toolkit version to the release version in the following files:
 * Constant SOITOOLKIT_VERSION in tools/soitoolkit-generator/soitoolkit-generator/src/main/java/org/soitoolkit/tools/generator/model/impl/DefaultModelImpl.java
 * commons/poms/default-parent/pom.xml" --> "/ns:project/ns:properties/ns:soitoolkit.version"
* Make sure the default Mule version for the Maven-generator plugin is among valid version in 
 * tools/soitoolkit-generator/soitoolkit-generator-maven-plugin/src/main/java/org/soitoolkit/tools/generator/maven/GenIntegrationComponentMojo.java
* `mvn clean test`
* `git commit -m "Commit for releasing v0.4.0"`
* `mvn release:clean release:prepare -DdryRun=true`
* `mvn release:prepare`
* `mvn release:perform`
* Go to Sonatypes staging repository and release it to synch with maven central repo
 * Go to: https://oss.sonatype.org
 * Login to the Nexus UI.
 * Go to Staging Repositories page.
 * Select a staging repository.
 * Select the soi-toolkit release
 * Click the Close button.
* Validate and so on...
* Merge back master to develop (or from the release branch?)
* Delete release branch if used


# Sample usage

    $ mvn org.soitoolkit.tools.generator:soitoolkit-generator-maven-plugin:2.0.0-M2-SNAPSHOT:genICV2
    $ cd sample1
    $ mvn org.soitoolkit.tools.generator:soitoolkit-generator-maven-plugin:2.0.0-M2-SNAPSHOT:genServiceV2
    $ mvn org.soitoolkit.tools.generator:soitoolkit-generator-maven-plugin:2.0.0-M2-SNAPSHOT:genServiceV2 -Dservice=oneway1 -DmessageExchangePattern=One-Way -DinboundTransport=JMS -DoutboundTransport=JMS
    $ mvn install
    
Enjoy!    
