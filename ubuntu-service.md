[Unit]
Description=App Webserver
After=mysql.service
Requires=mysql.service

[Service]
ExecStart=/usr/bin/java -Dlogging.file.path=/home/App/logs -Dspring.jpa.show-sql=false -Dlogging.level.org.springframework=ERROR -Dlogging.file=true -jar /home/App/app.jar
User=App
WorkingDirectory=/home/App

[Install]
WantedBy=multi-user.target
