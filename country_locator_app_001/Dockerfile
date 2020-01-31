FROM restio/ibmace:11.0.0.6

# Maintainer Srivatsa

# Custom Scripts for the microservice -- country-locator-app
COPY odbc.ini /home/aceuser/ace-server/odbc
COPY odbcinst.ini /home/aceuser/ace-server/odbc
COPY setdbparms.txt /home/aceuser/initial-config/setdbparms
COPY target/ace/country_locator_app_001.bar /home/aceuser/initial-config/bars

# Set DB params
RUN /home/aceuser/set-db-parms

# Deploy Bar
RUN /home/aceuser/set-bars-deploy
