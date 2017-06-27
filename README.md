# linux-configuration
 Linux server preparation to host a web application.
# Run
To view the deployed catalog-app project, you need to add the below string to your `hosts` file:
35.158.162.144 catalog-app.com
After that you can access http://catalog-app.com to view the catalog application. 

## Deplyment information
This project is using [Amazon lightsail](https://lightsail.aws.amazon.com/) that gives a publicly accessible Ubuntu Linux server.
IP address: 35.158.162.144
SSH port is changed to 2200
Uncomplicated Firewall (UFW) is configured to only allow incoming connections for SSH (port 2200), HTTP (port 80), and NTP (port 123).
All application dependences were installed to clone and run the application, such as Git, PostegreSQL, Flask, Sqlalchemy.
