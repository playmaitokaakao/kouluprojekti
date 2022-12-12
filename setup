The salt state in question can be used easily. All you have to do is setup a salt-master and salt-minion architecture and 
create a new directory for your salt-state in your salt directory which has the sls in it.
You can do this on Ubuntu by using the following commands:

SETTING UP SALT MASTER AND MINION

ON THE MASTER:

sudo apt-get update
sudo apt-get -y install salt-master
hostname -I

# Keep the hostname in mind or write it down.

ON THE MINION:

sudo apt-get update
sudo apt-get -y install salt-minion
sudoedit /etc/salt/minion

Inside of the /etc/salt/minion file you will write the following:

master: (the IP address of the master that you found out with hostname -I)
id: (the name you want the master to see your minion as)

sudo systemctl restart salt-minion.service

After you restart the salt-minion with the command you need to execute these commands on the master computer.

ON THE MASTER:

sudo systemctl restart salt-master.service
sudo salt-key -A

After you're asked if you want to proceed:

y

CREATING THE SALT-STATE ON THE MASTER:

Now that you've installed salt properly you can go to your /srv/salt directory.
You can navigate directories with the ls and cd commands for example if you're in the /srv directory you can get to /srv/salt
by using cd salt.

In the salt directory you'll create a directory that you can name by yourself by using the following command:
sudo mkdir (the name you want for the directory)

Inside of the directory you'll create an sls file and open it by using the following command:
sudo nano init.sls

Now inside of the init.sls file you're going to type or copy the following text:
gnome:
  pkg.installed

apache2:
  pkg.installed

ufw:
  pkg.installed
  
RUNNING THE SALT-STATE ON THE MASTER:

After this you can run the salt state and it will begin installing the packages on your minion.
You can do this by running the following command on the master:

sudo salt '*' state.apply (the folder's name which the init.sls file resides in)

in my case this was:
sudo salt '*' state.apply all

This project was made for Haaga-Helia course Palvelinten hallinta - ICT4TN022-3018 - ph 2022p2

![Kuva onnistuneesta state.applysta](https://github.com/playmaitokaakao/kouluprojekti/blob/main/kuvat/asennukset.png)

