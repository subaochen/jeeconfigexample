# jeeconfigexample

Sample JEE 7 application to demonstrate custom deltaspike properties file configuration and adjusted arquillian tests using embedded wildfly.

The application skeleton was generated with JBOSS Forge tool.

Add datasource.cli via jboss.cli command like in the root porojects directory assuming that wildfly 8.2 is already started
**${wildfly_home}\bin\jboss.cli.bat  --file=datasource.cli**

To run arquillian tests execute:
**mvn clean package**

The default config file is **jeeconfigexample-config-dev.properties**  which can be overriden via sytem or environment variables. 

To customize the properties file name depending on the actual environment set the environment  **jeeconfigexampleStage** (example: export jeeconfigexampleStage=test) or system property variable to the desired value (example: -DjeeconfigexampleStage=test), supposing that **jeeconfigexample-config-{cutomenv}.properties** (example: jeeconfigexample-config-test.properties) is on the classpath.
In the name selection of actual properties file the environment variable has higher precedence order than system property variable following the deltaspike default precedence order.

All deltaspike's key order precedence is untouched so precedence order are: environment variables, system properties, properties file.

Using Wildly to deploy the application the url:
**http://localhost:8080/jeeconfigexample/jeeconfigexample**




