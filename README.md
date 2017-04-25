# Nginx-logstash-example
Sample Logstash NGINX config log parser

<br />
<br />

CONTENTS:
<br />
- nginx.conf
<br /> Configuration file which defines the log format, and also applies the format to the nginx access.log
- logstash.conf
<br /> Configuration file which defines the logstash input file (nginx/access.log), and is set to output to stdout to test this simple setup.
- access.log
<br /> Example log file to take as input for logstash. This logs requests made to the nginx server setup on http://localhost:80
<br />
<br />
<br />


ENVIRONMENT SETUP:
<br />
This setup was done with both nginx and logstash running locally.
<br />
nginx.conf located in /etc/nginx/
<br />
logstash.conf located in /etc/logstash/
<br />
access.log located in /var/log/nginx/

<br />
<br />
<br />
To test, make sure nginx and logstash are running with the following commands

<br />
Nginx:
<br />
sudo systemctl start nginx
<br />
sudo ufw allow 'Nginx HTTP'
<br />
systemctl status nginx

<br />
<br />
Logstash:
<br />
/opt/logstash/bin/logstash -f /etc/logstash/logstash.conf
<br />
<br />
Once logstash is running, and the nginx server is up locally, we can make get requests to the page http://localhost:80, which should create a log entry in access.log, and we can see the printed output to stdout
