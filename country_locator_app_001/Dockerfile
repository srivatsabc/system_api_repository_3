FROM restio/ibmace:11.0.0.6

# Custom Scripts for the microservice -- country-locator-app
COPY --chown=aceuser odbc.ini /home/aceuser/ace-server/odbc
COPY --chown=aceuser odbcinst.ini /home/aceuser/ace-server/odbc
COPY --chown=aceuser setdbparms.txt /home/aceuser/initial-config/setdbparms
COPY --chown=aceuser country_locator_app_001/target/ace/country_locator_app_001.bar /home/aceuser/initial-config/bars

# Set DB params
RUN /home/aceuser/set-db-parms

# Deploy Bar
RUN /home/aceuser/set-bars-deploy
