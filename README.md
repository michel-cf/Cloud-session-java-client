# Cloud-Session
Authentication system for cloud-compiled projects, and also provides a configurable rate limiting system.

All services are provided as rest services that return json. They should not be called by the users browser or client side application but by the servers on a private network.

## Terminology
- Local user: registered using an email and password. They'll have to confirm their email address and request password reset tokens.
- OAuth user: users registered through a third party authentication service. They cannot change their password through this server, nor have to confirm their email address.


## Manuals
### Building
As this is a maven project, all dependencies will be downloaded by maven. To create a war file execute **mvn clean package** in the root directory.

### Mysql setup
Create a schema and if wanted a user and import the [table definitions](cloudsession-schema.sql).

A different database can be used, but the sql might need to be changed and configuration will be needed.

### Configuration
Create a text file with the name **cloudsession.properties** and put in configurations as described in the [configuration manual](CONFIGURATION.md).

### Deployment
Set the generated or downloaded war into the webapps directory of your tomcat and start it.
