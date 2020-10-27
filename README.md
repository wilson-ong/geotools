# debug-geoserver-2.16.0
Branch out to debug geoserver 2.16.0 issue.

## Building

Download [Apache Maven](http://maven.apache.org/) and [JDK 1.8](https://www.oracle.com/java/technologies/javase/javase-jdk8-downloads.html).

To build the library run maven from the root of the repository.

    % mvn install -DskipTests -Drelease 
    
### Install
Copy the `*-22.0.jar` from `$USER_HOME/.m2` on your device to `$CATALINA_HOME/webapps/geoserver/WEB-INF/lib` on server.

## Logging for debug
### [Optional] Enable detailed logging output in geoserver
From geoserver web UI, go to `Settings/Global` and select *verbose* debugging profile, 
then change all the log levels in `${GEOSERVER_DATA_DIR}/logs/VERBOSE_LOGGING.properties` to `ALL`.


### Insert logging in code
1. Make sure `LOGGER` is declared on class level.
2. Use `LOGGER.warning("Testing")` to log.
 
### Read log output
If you did not enable detailed logging output in geoserver Use `tail -f ${CATALINA_HOME}/logs/catalina.out` to read the output.

Else you can find the log file at `${GEOSERVER_DATA_DIR}/logs/geoserver.log`.
