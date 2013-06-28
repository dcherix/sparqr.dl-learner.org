sparqr.dl-learner.org
=====================

SPARQR: SPARQL Query Recommender Demo Releases of DL-Learner


## Start the webapp
The tomcat7-maven-plugin were used to create this webapp. To start the webapp just give `java -Xms1G -Xmx2G -jar dl-learner-standalone.jar -loggerName slf4j [--options=value]`. You can see a list of possibles options by typing `java -jar dl-learner-standalone.jar --help`.
	
	usage: java -jar [path to your exec war jar]
		-ajpPort <ajpPort>                     ajp port to use
		-clientAuth                            enable client authentication for https
		-D <arg>                               key=value
		-extractDirectory <extractDirectory>   path to extract war content, default value: .extract
		-h,--help                              help
		-httpPort <httpPort>                   http port to use
		-httpProtocol <httpProtocol>           http protocol to use: HTTP/1.1 or org.apache.coyote.http11.Http11Nio Protocol
		-httpsPort <httpsPort>                 https port to use
		-keyAlias <keyAlias>                   alias from keystore for ssl
		-loggerName <loggerName>               logger to use: slf4j to use slf4j bridge on top of jul
		-obfuscate <password>                  obfuscate the password and exit
		-resetExtract                          clean previous extract directory
		-serverXmlPath <serverXmlPath>         server.xml to use, optional
		-uriEncoding <uriEncoding>             connector uriEncoding default ISO-8859-1
		-X,--debug                             debug
 		
## Using the webapp
The service is available under [http://localhost:8080/interfaces/rest](http://localhost:8080/interfaces/rest). 

To use the DL-learner you must past a configuration to the webapp. At example the command: `curl --data-urlencode  conf@examples/AristotlePosNeg.conf  "http://127.0.0.1:8080/interfaces/rest"` send the AristotlePosNeg configuration to the webapp and wait for the answer of the DL-learner.

##Examples
In the folder "examples" are examples config files. All the config files uses the [new SPARQL-component](http://jens-lehmann.org/files/2012/jist_dllearner_sparql.pdf). The SPARQL component enables to work on data located in a triple store, the new SPARQL component improve the performance of the data recovering from triple store.

### AristotlePosNeg(
`curl --data-urlencode  conf@examples/AristotlePosNeg.conf  "http://127.0.0.1:8080/interfaces/rest"`
	
The AristotlePosNeg example show an example of learning wit positives and negatives examples. The learning problem is based on DBpedia.

### St George Dragons Players
`curl --data-urlencode  conf@examples/StGeorge.conf  "http://nlp2rdf/interfaces/rest"`
	
This example uses a list of rugby players of the St George Dragons and some others players.
The result is a definition to retrieve all St George Dragons players.
