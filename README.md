## <Check_operating_system> ::
head -n 2 /etc/os-release
## <user> ::
# Adding user in sudo group :
su -
usermod -aG sudo your_username
# Check if user is in sudo group :
getent group sudo
# creating new user :
sudo adduser username 
# Verify password expire info for new user :
sudo chage -l username
# assign new user to sudo and user42 groups :
sudo adduser username (sudo/user42)
#### <Create_group> ####
sudo groupadd (group_name)
==> check if group created : getent group
# Assign an user into “evaluating” group :
sudo usermod -aG (group_name) (new_username)
# check if the user is in group :
getent group (group_name)
# Check which groups user account belongs :
groups
## <PASSWORD> ::
# Set password policy :
sudo vim /etc/pam.d/common-password
# Password expiration :
sudo vim /etc/login.defs
## <hostname> ::
# Check current hostname :
hostname
hostnamectl
# change the hostname :
hostnamectl set-hostname (new_hostname)
## <partitions> ::
# view the partitions :
lsblk
## <sudo> ::
# Check sudo is installed :
dpkg -l | grep sudo
# Adding user in sudo group :
su -
usermod -aG sudo your_username
## <UFW> ::
# UFW Check the status :
sudo ufw status
sudo ufw status numbered
# Configure the rules :
sudo ufw allow ssh
# configure the port rules :
sudo ufw allow 4242
# Delete the new rule :
sudo ufw status numbered
sudo ufw delete (that number)
==> Restart SSH server : sudo systemctl restart ssh
==> check ssh status : sudo service sshd status
## <SSH> ::
# Check the SSH server status :
sudo service ssh status
sudo systemctl status ssh
# Restart the SSH service :
service ssh restart
# Changing default port (22) to 4242 :
sudo vim /etc/ssh/sshd_config
# Check if port settings got right :
sudo grep Port /stc/ssh/sshd_config
