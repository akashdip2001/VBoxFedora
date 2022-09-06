<img align="left" alt="Coding" width="100" src="https://getfedora.org/static/images/fedora-logofull-blue.png">
<img align="left" alt="Coding" width="100" src="https://www.virtualbox.org/graphics/vbox_logo2_gradient.png">

# install VirtualBox on Fedora?

How to install VirtualBox on Fedora?
<img align="right" alt="Coding" width="100" src="https://yt3.ggpht.com/7tPHyFi7-QyTnhpc484ZzTuRp0fZSY-CUuykvzuKdKYIwt0fmw98SWMqwRy_7pZ6LQzEYJlvXA=s88-c-k-c0x00ffffff-no-rj-mo">

## Installation

Before installing VirtualBox, it is recommended to perform an OS upgrade:

```
sudo dnf -y upgrade && sudo reboot
```

**1. Install all the required dependencies:**

```
sudo dnf -y install @development-tools && sudo dnf -y install kernel-headers kernel-devel dkms elfutils-libelf-devel qt5-qtx11extras
```

2. **Add VirtualBox RPM repository depending on your Fedora version:**
   *Fedora 35/34*

```
cat <<EOF | sudo tee /etc/yum.repos.d/virtualbox.repo 
[virtualbox]
name=Fedora $releasever - $basearch - VirtualBox
baseurl=http://download.virtualbox.org/virtualbox/rpm/fedora/34/\$basearch
enabled=1
gpgcheck=1
repo_gpgcheck=1
gpgkey=https://www.virtualbox.org/download/oracle_vbox.asc
EOF
```

*Fedora 33*

```
cat <<EOF | sudo tee /etc/yum.repos.d/virtualbox.repo 
[virtualbox]
name=Fedora $releasever - $basearch - VirtualBox
baseurl=http://download.virtualbox.org/virtualbox/rpm/fedora/33/\$basearch
enabled=1
gpgcheck=1
repo_gpgcheck=1
gpgkey=https://www.virtualbox.org/download/oracle_vbox.asc
EOF
```

*Fedora 32*

```
cat <<EOF | sudo tee /etc/yum.repos.d/virtualbox.repo 
[virtualbox]
name=Fedora $releasever - $basearch - VirtualBox
baseurl=http://download.virtualbox.org/virtualbox/rpm/fedora/32/\$basearch
enabled=1
gpgcheck=1
repo_gpgcheck=1
gpgkey=https://www.virtualbox.org/download/oracle_vbox.asc
EOF
```
*Fedora 31*

```
cat <<EOF | sudo tee /etc/yum.repos.d/virtualbox.repo 
[virtualbox]
name=Fedora $releasever - $basearch - VirtualBox
baseurl=http://download.virtualbox.org/virtualbox/rpm/fedora/31/\$basearch
enabled=1
gpgcheck=1
repo_gpgcheck=1
gpgkey=https://www.virtualbox.org/download/oracle_vbox.asc
EOF
```
*Fedora 30*

```
cat <<EOF | sudo tee /etc/yum.repos.d/virtualbox.repo 
[virtualbox]
name=Fedora $releasever - $basearch - VirtualBox
baseurl=http://download.virtualbox.org/virtualbox/rpm/fedora/30/\$basearch
enabled=1
gpgcheck=1
repo_gpgcheck=1
gpgkey=https://www.virtualbox.org/download/oracle_vbox.asc
EOF
```

3. **Import VirtualBox GPG Key:**

```
sudo dnf search virtualbox
```
Press "Y" when prompted

4. **Install VirtualBox 6.1:**

```
sudo dnf install VirtualBox-6.1
```
5. **Add your user to the vboxusers group:**

```
sudo usermod -a -G vboxusers $USER && newgrp vboxusers
```

To verify:

```
id $USER
```
This should return groups=976(vboxusers)


## 6. (recommended) Reboot your PC
## Thank you
<img align="left" alt="Coding" width="100" src="https://getfedora.org/static/images/fedora-logofull-blue.png">
<img align="right" alt="Coding" width="100" src="https://getfedora.org/static/images/g-monitor-fedoralogo.png">

