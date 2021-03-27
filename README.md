# 2420week11
This service runs a script that provides hourly weather updates from https://wttr.in/.

1. Move motd.service and motd.timer into the /etc/systemd/system directory

  >`sudo mv motd.service /etc/systemd/system`
  >
  >`sudo mv motd.timer /etc/systemd/system`

2. If the /home/vagrant/scripts directory does not exist, create it.

  >`cd ~`
  >
  >`mkdir scripts`

3. Ensure you have executable permissions for the wttr.sh file.

  >`chmod 777 wttr.sh`

4. Move wttr.sh to the /home/vagrant/scripts directory. 

  >`mv wttr.sh ~/scripts`

5. Reload the daemon list.

  >`sudo systemctl daemon-reload`
  
6. Start the timer

  >`sudo systemctl start motd.timer`

---
  
Every hour the script will write the weather updates to /home/etc/motd.

You can check the output by entering the following command into the terminal:
  
  >`cat /etc/motd`
  
