# graylog


How to Use the Script
Step 1: Save the Script

# Create the script file
sudo nano /tmp/install_graylog.sh

# Copy the entire script above and paste
# Save: CTRL+O, Enter, CTRL+X

Step 2: Make it Executable

sudo chmod +x /tmp/install_graylog.sh


Step 3: Run the Script
# Run as root
sudo /tmp/install_graylog.sh


After Installation
Once the script completes:

Access Graylog:

text
http://YOUR_SERVER_IP:9000
Login:

Username: admin

Password: admin@123 (or what you set)

Complete Preflight Setup:

Follow the wizard

Configure your inputs (Syslog, GELF, etc.)



🛠️ Troubleshooting
Check Service Status

sudo systemctl status graylog-server
sudo systemctl status graylog-datanode
sudo systemctl status mongod


Check Logs
sudo tail -100 /var/log/graylog-server/server.log
sudo tail -100 /var/log/graylog-datanode/datanode.log
sudo tail -100 /var/log/mongodb/mongod.log


Restart All Services

sudo systemctl restart mongod
sleep 5
sudo systemctl restart graylog-datanode
sleep 10
sudo systemctl restart graylog-server


# One-Line Installation
curl -sSL https://raw.githubusercontent.com/your-repo/install_graylog.sh | sudo bash







