NOTE:  MUST be a root user
Creating Service in ubuntu

1. create service file
sudo nano /lib/systemd/system/myservice.service

2. Create service file
[Unit]
Description=myservice Service
After=multi-user.target

[Service]
User=ubuntu
Type=simple
WorkingDirectory=/home/ubuntu/myservice/
ExecStart=/usr/bin/python3 sudo /home/ubuntu/myapp.py

[Install]
WantedBy=multi-user.target



3. Reload Service
sudo systemctl daemon-reload

4. Enable Service
sudo systemctl enable myservice.service

5. Start Service
sudo systemctl start myservice.service

6. Check Status
sudo systemctl status myservice.service



Now you have the service which can run even when you reboot system
