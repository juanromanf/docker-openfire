FROM gizmotronic/openfire:4.2.3

COPY --chown=openfire:openfire mysql-connector-java-8.0.12.jar /usr/share/openfire/lib/mysql.jar
COPY --chown=openfire:openfire openfire_mysql.sql /usr/share/openfire/resources/database/openfire_mysql.sql

#COPY --chown=openfire:openfire openfire.xml /var/lib/openfire/conf/openfire.xml
#COPY --chown=openfire:openfire log4j.xml /var/lib/openfire/conf/log4j.xml

#COPY --chown=openfire:openfire plugins/monitoring.jar /var/lib/openfire/plugins/monitoring.jar
#COPY --chown=openfire:openfire plugins/restAPI.jar /var/lib/openfire/pluginsrestAPI.jar
#COPY --chown=openfire:openfire plugins/userImportExport.jar /var/lib/openfire/plugins/userImportExport.jar
#COPY --chown=openfire:openfire plugins/userStatus.jar /var/lib/openfire/plugins/userStatus.jar