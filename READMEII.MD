Archipel Instalación para Fedora23 (Hetzner VNC)

How do I start a VNC installation?
To start a VNC installation, click on the "VNC" tab of your server in Robot. 
Here you will see a dropdown list of available operating systems, as well as the architecture and the language. 
After selecting the configuration you want, and pressing the activate button, a password will be displayed with which you can login to the VNC installation, a few minutes after you restart the server

VNC Client: IP:1 + Password (Configure Instalación) + Reboot

Installing KVM packages:::::::::::::::::::::::::::::::::::::

yum install kvm

yum install virt-manager libvirt libvirt-python python-virtinst

yum install qemu

yum install gcc
cd /usr/src
wget https://www.python.org/ftp/python/2.7.10/Python-2.7.10.tgz
tar xzf Python-2.7.10.tgz
cd Python-2.7.10
./configure
make altinstall
python2.7 -V

sudo dnf upgrade python-setuptools
sudo dnf install python-pip python-wheel

yum install python-devel zlib-devel 
yum install easy_install pip
sudo easy_install Pillow 
sudo pip install Pillow

yum install numpy scipy python-matplotlib ipython python-pandas sympy python-nose atlas-devel
yum -y install git

git clone https://github.com/ArchipelProject/Archipel.git
cd /path/to/clone/Archipel/
./pull.sh

easy_install apscheduler==2.1.2 sqlalchemy numpy
cd /path/ArchipelAgent/
./buildAgent -d

archipel-initinstall

archipel-tagnode --jid=admin@FQDN --password=YOURPASSWORD --create
archipel-rolesnode --jid=admin@FQDN --password=YOURPASSWORD --create
archipel-adminaccounts --jid=admin@FQDN --password=YOURPASSWORD --create

/etc/init.d/archipel start

archipel-testxmppserver --jid=admin@FQDN --password=YOURPASSWORD

