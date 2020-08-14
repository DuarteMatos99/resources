###### tags: `Networking`, `Servers`, `Linux`
# Linux Services

## DHCP

**1.** 
```
nano /etc/dhcp/dhcpd.conf
```

**2.** INTERFACES = “enp0s8”;
subnet 192.168.1.0 netmask 255.255.255.0 {
range 192.168.1.20 192.168.1.100; (Esta range vai defenir de onde começam os ips dados e onde acabam )
Option routers 192.168.1.1; (Este comando e o que se enconta abixo fazem com que seja possivél ver o default-gateway nas máquinas que se encontram a receber ip’s do server )
Option domain-name-servers 192.168.1.1;
}

**3.**
```
service isc-dhcp-server restart
```


## Apache2

**1.** 
```
sudo apt update
sudo apt install apache2
```

**2.** So let's start by creating a folder for our new website in /var/www/ by running
```
sudo mkdir /var/www/gci/
```

**3.** We have it named gci here but any name will work, as long as we point to it in the virtual hosts configuration file later.

Now that we have a directory created for our site, lets have an HTML file in it. Let's go into our newly created directory and create one by typing:
```
cd /var/www/gci/
nano index.html
```

**4.** Paste the following code in the index.html file:
```
<html>
<head>
  <title> Ubuntu rocks! </title>
</head>
<body>
  <p> I'm running this website on an Ubuntu Server server!
</body>
</html>
```

**5.** We start this step by going into the configuration files directory:
```
cd /etc/apache2/sites-available/
```

**6.** Since Apache came with a default VirtualHost file, let's use that as a base. (gci.conf is used here to match our subdomain name):
```
sudo cp 000-default.conf gci.conf
```

**7.** Now edit the configuration file:
```
sudo nano gci.conf
```

**8.** We should have our email in ServerAdmin so users can reach you in case Apache experiences any error:
```
ServerAdmin yourname@example.com
```

**9.** We also want the DocumentRoot directive to point to the directory our site files are hosted on:
```
DocumentRoot /var/www/gci/
```

**10.** The default file doesn't come with a ServerName directive so we'll have to add and define it by adding this line below the last directive: 
```
ServerName gci.example.com
```

**11.** After setting up our website, we need to activate the virtual hosts configuration file to enable it.
We do that by running the following command in the configuration file directory:
```
sudo a2ensite gci.conf
```

**12.** You should see the following output
```
Enabling site gci.
To activate the new configuration, you need to run:
  service apache2 reload
root@ubuntu-server:/etc/apache2/sites-available#
```

**13.** To load the new site, we restart Apache by typing:
```
service apache2 reload
```

**14.** Now is the moment of truth, let's type our host name in a browser.
![](https://i.imgur.com/MTSOFGg.png)


**15.** Enter the file:
```
nano /etc/hosts/
```

**16.** Use your ip server and the name of your site
![](https://i.imgur.com/EtZifvH.png)

## Samba

**1.** To install Samba, we run:
```
sudo apt update
sudo apt install samba
```

**2.** We can check if the installation was successful by running:
```
whereis samba
```

**3.** The following should be its output:
```
samba: /usr/sbin/samba /usr/lib/samba /etc/samba /usr/share/samba /usr/share/man/man7/samba.7.gz /usr/share/man/man8/samba.8.gz

```

**4.** Now that Samba is installed, we need to create a directory for it to share:
```
mkdir /home/<username>/sambashare/
```

**5.** The command above creates a new folder sambashare in our home directory which we will share later.

The configuration file for Samba is located at /etc/samba/smb.conf. To add the new directory as a share, we edit the file by running:
```
sudo nano /etc/samba/smb.conf
```

**6.** At the bottom of the file, add the following lines:
```
[sambashare]
    comment = Samba on Ubuntu
    path = /home/username/sambashare
    read only = no
    browsable = yes
```
Then press ==Ctrl-O== to save and ==Ctrl-X== to exit from the nano text editor.

**What we've just added**

==[sambashare]:== The name inside the brackets is the name of our share.
==comment:== A brief description of the share.
==path:== The directory of our share.
==read only:== Permission to modify the contents of the share folder is only granted when the value of this directive is no.
==browsable:== When set to **yes**, file managers such as Ubuntu's default file manager will list this share under "Network" (it could also appear as browseable).

**7.** First we need to create users:
```
useradd <username>
```

**8.** Since Samba doesn't use the system account password, we need to set up a Samba password for our user account:
```
sudo smbpasswd -a username
```
==Note==
Username used must belong to a system account, else it won't save.

**9.** Restart the service:
```
service smbd restart
```

**10.** On ==Ubuntu==:
Open up the default file manager and click Connect to Server then enter:
![](https://i.imgur.com/TxZQfKF.png)


**11.** On ==Windows==, open up File Manager and edit the file path to:
```
\\ip-address\sambashare
```

## Ip Tables 

**1.**
```
iptables -t nat -A POSTROUTING -o enp0s3 -j MASQUERADE
```

**2.**
```
iptables -A FORWARD -i enp0s8 -o enp0s3 -j ACCEPT
```

**3.**
```
apt-get install iptables-persistent
```

**4.**
```
nano /etc/sysctl.conf
```

**5.** Uncomment
```
net.ipv4.ip_forward=1
```

**6.**
```
service networking restart
```

### Block sites
In order to block our customers from visiting certain websites, we following codes (in which the mac address is the one corresponding to the machines of the clients that we want to block traffic):

**1.** For the Windows client, you will not be able to access facebook.com:
```
iptables -I FORWARD -m string --algo bm --string &quot;facebook.com&quot; -m mac --mac- source 08:00:27:4C:05:59 -j DROP
```

## Asterisk 

**1.**
```
apt-get install asterisk
```

**2.** Configure the extensions 100 and 101:
```
nano /etc/asterisk/sip.conf
```

**3.** Write the next words in the end:
![](https://i.imgur.com/vh9FsYb.png)

**4.** Now we gonna register the users that our customers will have
```
nano /etc/asterisk/users.conf
```

**5.** Write the next words in the end:
![](https://i.imgur.com/myQPemo.png)

**6.** Finally we will add the extensions in the asterisk service
```
/etc/asterisk/extensions.conf
```

**7.** Write the next words in the end:

![](https://i.imgur.com/gFux9hj.png)

**8.** To finish the installation we enter the asterisk console with the command **asterisk -r**
and we execute a **restart core**

### Installing Zoiper on Windows (VOIP client)

**1.** Let's now install the VOIP client on both Windows clients so that communicate between them, in the web browser we go to the site www.zoiper.com and we do download the service and make the proper installation

![](https://i.imgur.com/qkUgCkw.png)

**2.** Insert the extension that we insert into the files that we edit and also insert the password as shown in the image

![](https://i.imgur.com/KP1tz1E.png)

**3.** Then we put the ip of the server and the respective port that in this case is the 5060

![](https://i.imgur.com/oylA83z.png)

**4.** Finally, with the extensions configured on both machines we can doa call between the two

![](https://i.imgur.com/xnnAHKx.png)

## Serviço Web Chat
Initial configuration includes OpenFire. Check this site:
```
https://computingforgeeks.com/how-to-install-openfire-xmpp-chat-server-on-ubuntu-18-04-ubuntu16-04/
```

### Spark (Linux)

**1.** Let's now install Spark, a webchat service, we start by running the
following command
```
wget http://download.igniterealtime.org/spark/spark_2_8_2.tar.gz
```

**2.** To proceed with the installation we execute the following commands:
```
sudo tar -zxvf spark_2_8_2.tar.gz -C /opt/
sudo mv /opt/Spark/ /opt/spark
cd /opt/spark/
sudo nano /usr/share/applications/spark.desktop
```

**3.** And copy the following commands to the spark.desktop

![](https://i.imgur.com/itIMJpz.png)

**4.** Execute the Spark program:

![](https://i.imgur.com/ZG7EjkX.png)

### Spark (Windows)

**1.** Open a web browser and go to URL:
```
https://igniterealtime.org/downloads/index.jsp#spark –Windows
```

**2.** Repeat the same steps, but in this time use another user

![](https://i.imgur.com/y3UL9FE.png)

**3.** In the end we need to try the connection

![](https://i.imgur.com/n8C50Ve.png)
