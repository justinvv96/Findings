How to fix certificate issue with java
======================================
1. download certifcate from corresponding website
2. Add the downloaded certifcate to the keystore
   keytool -importcert -file jenkins.crt -keystore jenkins.keystore -alias update.jenkins
   Note: you can create a custom keystore and which need to pass to jvm
         otherwise we need to add file jvm keystore
3. Once certificated added to keystore. you can use the application
   java -Djavax.net.ssl.trustStore=jenkins.keystore -Djavax.net.ssl.trustStorePassword=abcd1234 -jar jenkins.war
