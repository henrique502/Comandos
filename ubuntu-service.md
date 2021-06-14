[Unit]
Description=Service Webserver
After=mysqld.service
Requires=mysqld.service

[Service]
ExecStart=/usr/bin/java -Dlogging.path=/home/service/logs -Dlogging.level.org.springframework=ERROR -jar /home/service/app.jar
User=service

[Install]
WantedBy=multi-user.target
