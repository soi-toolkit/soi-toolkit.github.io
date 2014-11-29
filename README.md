soi-toolkit.github.io
=====================

GitHub Pages

Sample usage:

    $ mvn org.soitoolkit.tools.generator:soitoolkit-generator-maven-plugin:2.0.0-M2-SNAPSHOT:genICV2
    $ cd sample1
    $ mvn org.soitoolkit.tools.generator:soitoolkit-generator-maven-plugin:2.0.0-M2-SNAPSHOT:genServiceV2
    $ mvn org.soitoolkit.tools.generator:soitoolkit-generator-maven-plugin:2.0.0-M2-SNAPSHOT:genServiceV2 -Dservice=oneway1 -DmessageExchangePattern=One-Way -DinboundTransport=JMS -DoutboundTransport=JMS
    $ mvn install
    
Enjoy!    
