# Linux Server Configuration Project
 Linux server preparation to host a web application.
 This project uses [Amazon lightsail](https://lightsail.aws.amazon.com/) that gives a publicly accessible Ubuntu Linux server.
# Run
To view the deployed catalog-app project, you need to add the following string to `hosts` file on your PC:<br>
`35.158.162.144 catalog-app.com`
<br>After that you can access http://catalog-app.com to view the catalog application. 

## Deployment details
* SSH port was changed to 2200 in `/etc/ssh/sshd_config` file:
	* `Port 2200`
* Remote root login was disabled in `/etc/ssh/sshd_config` file:
	* `PermitRootLogin no`
* Key-based SSH authentication is enforced in `/etc/ssh/sshd_config` file:
	* `RSAAuthentication yes`
	* `PubkeyAuthentication yes`
* User `grader` was added:
	* `sudo adduser grader`
* The grader user can run commands using sudo to inspect files that are readable only by root:
	* Added `/etc/sudoers.d/grader` file
	* `sudo chmod 440 /etc/sudoers.d/grader`
* Apache web server installed and configured to serve a Python mod_wsgi application.
	* `sudo apt-get install apache2`
	* `sudo apt-get install libapache2-mod-wsgi`
* Checked that the local timezone is configured to UTC.
	* sudo more /etc/timezone
* Uncomplicated Firewall (UFW) is configured to only allow incoming connections for SSH (port 2200), HTTP (port 80), and NTP (port 123).
	* `sudo ufw allow 2200/tcp`
	* `sudo ufw allow http`
	* `sudo ufw allow ntp`
* All application dependences were installed to clone and run the application, such as Git, PostegreSQL, Flask, Sqlalchemy.
	* `sudo apt install git`
	* `sudo apt-get install postgresql`
	* `sudo apt install python-pip`
	* `sudo pip install --upgrade pip`
	* `sudo pip install sqlalchemy`
	* `sudo pip install flask`
	* `sudo pip install oauth2client`
	* `sudo pip install requests`
  	* `sudo pip install psycopg2`

* PostegreSQL configuration files checked  for local connections permition only.
* New database user **catalog** created with limited permissions.

