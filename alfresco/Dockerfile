FROM alfresco/alfresco-content-repository-community:6.2.0-ga

ARG TOMCAT_DIR=/usr/local/tomcat

USER root

# Install modules and addons
RUN mkdir -p $TOMCAT_DIR/amps
COPY modules/amps $TOMCAT_DIR/amps
COPY modules/jars $TOMCAT_DIR/webapps/alfresco/WEB-INF/lib

RUN java -jar $TOMCAT_DIR/alfresco-mmt/alfresco-mmt*.jar install \
    $TOMCAT_DIR/amps $TOMCAT_DIR/webapps/alfresco -directory -nobackup -force

COPY lib/mysql-connector-java-8.0.13.jar $TOMCAT_DIR/lib
