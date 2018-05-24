## Setting up ssh on server and adding keys for easy login

### setup ssh on server
 * `sudo apt-get install openssh-server`
 * enable ssh and backup: 
 `sudo cp /etc/ssh/sshd_config /etc/ssh/sshd_config.factory-defaults`
 * modify permissions: 
 `sudo chmod a-w /etc/ssh/sshd_config.factory-defaults`
 * restart ssh: `sudo systemctl restart ssh`
 
### generate keys
 * `mkdir ~/.ssh`
 * change permissions: `chmod 700 ~/.ssh`
 * generate key: `ssh-keygen -t rsa`
 * to get the host ip: `ifconfig`
 * now can connect with `ssh [user on server ]@[server ip]`
 
### Simplify login from client
 * get public key on client side: `cat ~/.ssh/id_rsa.pub`
 * add key to: `~/.ssh/authorized_keys`, create it if doesn't
   exist
 * config host name on client side: 
   * open file `~/.ssh/config` and add:
      - Host [name]
      - HostName [server ip]
      - User [user on server]
   
To connect simply use: `ssh [name]` 


 
 