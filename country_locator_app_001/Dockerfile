FROM restio/ibmace:11.0.0.6

# Custom Scripts for the microservice -- country-locator-app
COPY odbc.ini /home/aceuser/ace-server/odbc
COPY odbcinst.ini /home/aceuser/ace-server/odbc
COPY setdbparms.txt /home/aceuser/initial-config/setdbparms
COPY country_locator_app_001/target/ace/country_locator_app_001.bar /home/aceuser/initial-config/bars

# Change ownership (as chown in COPY command failed)
RUN chown aceuser /home/aceuser/ace-server/odbc/odbc.ini && \
	chown aceuser /home/aceuser/ace-server/odbc/odbcinst.ini && \
	chown aceuser /home/aceuser/initial-config/setdbparms/setdbparms.txt && \
	chown aceuser /home/aceuser/initial-config/bars/country_locator_app_001.bar

# Set DB params
RUN /home/aceuser/set-db-parms

# Deploy Bar
RUN /home/aceuser/set-bars-deploy
