# Linux Server Configuration Project
 Linux server preparation to host a web application.
 This project uses [Amazon lightsail](https://lightsail.aws.amazon.com/) that gives a publicly accessible Ubuntu Linux server.
# Run
To view the deployed catalog-app project, you need to add the following string to `hosts` file on your PC:
`35.158.162.144 catalog-app.com`
<br>After that you can access http://catalog-app.com to view the catalog application. 

## Deployment details
* Installed and configured Apache web server to serve a Python mod_wsgi application.
* Checked that the local timezone is configured to UTC.
* SSH port is changed to 2200.
* Uncomplicated Firewall (UFW) is configured to only allow incoming connections for SSH (port 2200), HTTP (port 80), and NTP (port 123).
* New user with sudo permission created.
* All application dependences were installed to clone and run the application, such as Git, PostegreSQL, Flask, Sqlalchemy.
* Checked that there only local connections permitted in postegresql config.
* Created new database user **catalog** with limited permissions.

