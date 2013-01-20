A Java client for Etherpad Lite’s HTTP JSON API. Etherpad Lite is a collaborative editor provided by the Etherpad Foundation.

See https://github.com/ether/etherpad-lite for information on how to install and configure your own Etherpad Lite instance, and read http://etherpad.org/doc/v1.2.0/ for an in-depth description of Etherpad Lite’s HTTP API.

DOCUMENTATION
For now, the best documentation is reading through the methods available in the EPLiteClient class: https://raw.github.com/jhollinger/java-etherpad-lite/master/src/org/etherpad_lite_client/EPLiteClient.java. The methods are 1:1 with the EPLite API methods.

DEPENDENCIES
Depends on JSON.simple (http://code.google.com/p/json-simple/) version 1.1.1.

DOWNLOADS
You may download pre-compiled .jar files from http://jordanhollinger.com/etherpad-lite-java-client

NOTES
org.etherpad_lite_client uses Maven.

HEAD currently targets Etherpad Lite API v1.2.1. The plan is to keep up with the most recent version of the Etherpad Lite API. (Note that we're talking about API versions here, not release versions).

EXAMPLES
 EPLiteClient client = new EPLiteClient("http://etherpad.mysite.com", "FJ7jksalksdfj83jsdflkj");

 # Get pad text
 String text = client.getText("my_pad").get("text").toString(); 

 # Get list of all pad ids
 HashMap result = client.listAllPads();
 List padIds = (List) result.get("padIDs");

TESTING
Testing requires a copy of EtherpadLite running at http://localhost:9001 with an API key of K8OF91QMQYUvrNu3e9rJ7FnnVgaB3m9q
Run tests with maven:

 mvn test