# Installing Jenkins & Ansible
## Table Of Content
[Jenkins](#jenkins)

[Prerequsite](#prerequisites)

[Installing Jenkins](#installing-jenkins)

[Access Jenkins](#access-jenkins)

[Creating the First adminitration User](#creating-the-first-administrator-user)

[Jenkins Dashboard](#jenkins-dashboard)

[Create First Job](#create-first-job)

[Git & Github](#git--github)

[Build Preodically](#build-periodically)

[Poll SCM](#poll-scm)

[Ansible](#ansible)

[Install Ansible](#install-ansible)

[Testing ansible playbook](#testing-ansible-playbook)




# Jenkins:

Jenkins is an open source automation tool written in java that facilitates continuous integration and continuous delivery (CI/CD) in software development. That runs on Windows, Mac, Linux. It is free community support and a large number of plugins are available might be Your first choice tool CI. Jenkins automates the entire software development life cycle. Jenkins was developed by Sun micro system in 2004 under the hudson. Oracle buys and breaks Jenkins and hudson.

**Workflow:**

* We can attach Git, Mavon, Selenium and Artifactory plugins to Jenkins.
* Once a developer puts code in Github Jenkins puts the code & sends it to Maven for Build.
* Once Build is done Jenkins pulls that code and sends it to Selenium.
* Once testing is done Jenkins will pull that code and send it to Artifactory as per requirement and so on.
* We can deploy with Jenkins.

**Features:**

* It has a lot of plugins available.
* You can write your own plugins.
* You can use community plugins .
* Jenkins is not a tool It is also a framework.
* We can attach slaves to Jenkins. If slaves are not available Jenkins does itself job.

# Prerequisites:

* Minimum hardware requirements:

256 MB of RAM (Minimum)

1 GB of drive space

* Software requirements:

Java

# Installing Jenkins:

Before installing Jenkins, we install Java because if we install Jenkins first, an error will occur. 

Following are the steps included while installing Jenkins-
* Installing Java
* Download Jenkins Repository Key
* Add Jenkins Repository to APT Sources
* Update system
* Installing Jenkins
* Check the Jenkins service
  
**Installing Java:**
```
sudo apt-get install openjdk-11-jdk
```

**Output:**
```
vivek\@vivek-HP-EliteBook-840-G2:\~$ sudo apt-get install openjdk-11-jdk
Reading package lists... Done
Building dependency tree   
Reading state information... Done
The following packages were automatically installed and are no longer required:
  dctrl-tools dkms libdouble-conversion3 libgsoap-2.8.91 liblzf1 libpcre2-16-0
  libqt5core5a libqt5dbus5 libqt5gui5 libqt5network5 libqt5opengl5
  libqt5printsupport5 libqt5svg5 libqt5widgets5 libqt5x11extras5
  libsdl1.2debian libvncserver1 libxcb-xinerama0 libxcb-xinput0
  qt5-gtk-platformtheme qttranslations5-l10n virtualbox-dkms
Use 'sudo apt autoremove' to remove them.
The following additional packages will be installed:
  ca-certificates-java fonts-dejavu-extra libatk-wrapper-java
  libatk-wrapper-java-jni libice-dev libpthread-stubs0-dev libsm-dev
  libx11-dev libxau-dev libxcb1-dev libxdmcp-dev libxt-dev
  openjdk-11-jdk-headless openjdk-11-jre openjdk-11-jre-headless
  x11proto-core-dev x11proto-dev xorg-sgml-doctools xtrans-dev
Suggested packages:
  libice-doc libsm-doc libx11-doc libxcb-doc libxt-doc openjdk-11-demo
  openjdk-11-source visualvm fonts-ipafont-gothic fonts-ipafont-mincho
  fonts-wqy-microhei | fonts-wqy-zenhei
The following NEW packages will be installed:
  ca-certificates-java fonts-dejavu-extra libatk-wrapper-java
  libatk-wrapper-java-jni libice-dev libpthread-stubs0-dev libsm-dev
  libx11-dev libxau-dev libxcb1-dev libxdmcp-dev libxt-dev openjdk-11-jdk
  openjdk-11-jdk-headless openjdk-11-jre openjdk-11-jre-headless
  x11proto-core-dev x11proto-dev xorg-sgml-doctools xtrans-dev
0 upgraded, 20 newly installed, 0 to remove and 0 not upgraded.
Need to get 117 MB of archives.
After this operation, 275 MB of additional disk space will be used.
Do you want to continue? \[Y/n] y
Get:1 http\://archive.ubuntu.com/ubuntu focal-updates/main amd64 openjdk-11-jre-headless amd64 11.0.21+9-0ubuntu1\~20.04 \[38.3 MB]
Get:2 http\://archive.ubuntu.com/ubuntu focal-updates/main amd64 ca-certificates-java all 20190405ubuntu1.1 \[12.4 kB]
Get:3 http\://archive.ubuntu.com/ubuntu focal/main amd64 fonts-dejavu-extra all 2.37-1 \[1,953 kB]
Get:4 http\://archive.ubuntu.com/ubuntu focal/main amd64 libatk-wrapper-java all 0.37.1-1 \[53.0 kB]
Get:18 http\://archive.ubuntu.com/ubuntu focal-updates/main amd64 openjdk-11-jre amd64 11.0.21+9-0ubuntu1\~20.04 \[193 kB]
Get:19 http\://archive.ubuntu.com/ubuntu focal-updates/main amd64 openjdk-11-jdk-headless amd64 11.0.21+9-0ubuntu1\~20.04 \[73.7 MB]
Get:20 http\://archive.ubuntu.com/ubuntu focal-updates/main amd64 openjdk-11-jdk amd64 11.0.21+9-0ubuntu1\~20.04 \[1,332 kB]
Fetched 117 MB in 23s (5,081 kB/s)                         
Selecting previously unselected package openjdk-11-jre-headless:amd64.
(Reading database ... 202387 files and directories currently installed.)
Preparing to unpack .../00-openjdk-11-jre-headless\_11.0.21+9-0ubuntu1\~20.04\_amd64.deb ...
Unpacking openjdk-11-jre-headless:amd64 (11.0.21+9-0ubuntu1\~20.04) ...
Selecting previously unselected package ca-certificates-java.
Selecting previously unselected package openjdk-11-jre:amd64.
Preparing to unpack .../17-openjdk-11-jre\_11.0.21+9-0ubuntu1\~20.04\_amd64.deb ...
Unpacking openjdk-11-jdk:amd64 (11.0.21+9-0ubuntu1\~20.04) ...
Setting up libpthread-stubs0-dev:amd64 (0.4-1) ...
Setting up libatk-wrapper-java (0.37.1-1) ...
Setting up libatk-wrapper-java-jni:amd64 (0.37.1-1) ...
Setting up openjdk-11-jre-headless:amd64 (11.0.21+9-0ubuntu1\~20.04) ...
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/java to provide /usr/bin/java (java) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/jjs to provide /usr/bin/jjs (jjs) in auto mode
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/keytool to provide update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/jhsdb to provide /usr/bin/jhsdb (jhsdb) in auto mode
Setting up openjdk-11-jdk:amd64 (11.0.21+9-0ubuntu1\~20.04) ...
update-alternatives: using /usr/lib/jvm/java-11-openjdk-amd64/bin/jconsole to provide /usr/bin/jconsole (jconsole) in auto mode
Setting up ca-certificates-java (20190405ubuntu1.1) ...
head: cannot open '/etc/ssl/certs/java/cacerts' for reading: No such file or directory
Adding debian:Atos\_TrustedRoot\_2011.pem
Adding debian:DigiCert\_Global\_Root\_G2.pem
Adding debian:Starfield\_Class\_2\_CA.pem
Adding debian:Actalis\_Authentication\_Root\_CA.pem
Adding debian:DigiCert\_Trusted\_Root\_G4.pem
Adding debian:XRamp\_Global\_CA\_Root.pem
Adding debian:Certigna.pem

done.
Processing triggers for gnome-menus (3.36.0-1ubuntu1) ...
Processing triggers for man-db (2.9.1-1) ...
Processing triggers for ca-certificates (20230311ubuntu0.20.04.1) ...
Updating certificates in /etc/ssl/certs...
0 added, 0 removed; done.
Running hooks in /etc/ca-certificates/update.d…

done.
done.
Processing triggers for sgml-base (1.29.1) ...
Setting up x11proto-dev (2019.2-1ubuntu1) ...
Setting up libxau-dev:amd64 (1:1.0.9-0ubuntu1) ...
Setting up libice-dev:amd64 (2:1.0.10-0ubuntu1) ...
Setting up libsm-dev:amd64 (2:1.2.3-1) ...
Setting up libxdmcp-dev:amd64 (1:1.1.3-0ubuntu1) ...
Setting up x11proto-core-dev (2019.2-1ubuntu1) ...
Setting up libxcb1-dev:amd64 (1.14-2) ...
Setting up libx11-dev:amd64 (2:1.6.9-2ubuntu1.6) ...
Setting up libxt-dev:amd64 (1:1.1.5-1) ...
vivek\@vivek-HP-EliteBook-840-G2:\~$
```
**sudo**: This command is used to execute with superuser privileges. 

**apt-get**:This is the package management command. It is used for handling packages—installing, updating, and removing them.

**install**: This is an argument for the apt-get command, specifying that we want to install a package.

**openjdk-11-jdk**: This is the name of the package that we want to install. In this case, it is the OpenJDK 11 Java Development Kit.

* **Check Java:**
```
java --version
```
**Output:**
```
vivek\@vivek-HP-EliteBook-840-G2:\~$ java --version
openjdk 11.0.21 2023-10-17
OpenJDK Runtime Environment (build 11.0.21+9-post-Ubuntu-0ubuntu120.04)
OpenJDK 64-Bit Server VM (build 11.0.21+9-post-Ubuntu-0ubuntu120.04, mixed mode, sharing)
```

**java**: This is the command-line tool for executing Java applications.

**--version**: It typically prints information about the installed version of Java.

* **Download Jenkins Repository Key:**
```
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
```
**Output:**
```
vivek\@vivek-HP-EliteBook-840-G2:~$ sudo wget -O /usr/share/keyrings/jenkins-keyring.asc 
\>   https\://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
\--2023-12-30 15:02:22--  https\://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
Resolving pkg.jenkins.io (pkg.jenkins.io)... 2a04:4e42:42::645, 199.232.22.133
Connecting to pkg.jenkins.io (pkg.jenkins.io)|2a04:4e42:42::645|:443...
failed: Connection timed out.
Connecting to pkg.jenkins.io (pkg.jenkins.io)|199.232.22.133|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 3175 (3.1K) \[application/pgp-keys]
Saving to: ‘/usr/share/keyrings/jenkins-keyring.asc’
/usr/share/keyrings 100%\[===================>]   3.10K  --.-KB/s in 0s  
2023-12-30 15:04:34 (16.0 MB/s) - ‘/usr/share/keyrings/jenkins-keyring.asc’ saved \[3175/3175]
```
**sudo**: This is used to execute the following command with superuser privileges.

**wget**: This command is used to download files from the internet. 

**-O /usr/share/keyrings/jenkins-keyring.asc**: In this case, the file will be saved as jenkins-keyring.asc in the /usr/share/keyrings/ directory.

**<https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key>**: This is the URL from which wget will download the file. It's the Jenkins GPG key file (jenkins.io-2023.key) needed for package verification.

* **Add Jenkins Repository to APT Sources:**
```
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] 
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee 
  /etc/apt/sources.list.d/jenkins.list > /dev/null
```
**Output:**
```
vivek\@vivek-HP-EliteBook-840-G2:~$ echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] 
>   https://pkg.jenkins.io/debian-stable binary/ | sudo tee 
>   /etc/apt/sources.list.d/jenkins.list > /dev/null
```
**echo**: This command is used to print the text to the terminal.

**deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian-stable binary/**: This part specifies the APT repository information for Jenkins. It tells APT to use the specified GPG key file (jenkins-keyring.asc) for package verification and to fetch packages from the Jenkins repository.

**| sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null**: This part is used to write the output of the echo command to a file. The **tee** command is used to write to a file and also print to the terminal. sudo is used to execute the command with superuser privileges. The **> /dev/null** part discards the printed output.

* **Update System:** 
```
sudo apt-get update
```
**Output:**
```
vivek\@vivek-HP-EliteBook-840-G2:~$ sudo apt-get update
Hit:1 http\://security.ubuntu.com/ubuntu focal-security InRelease           
Hit:2 https\://dl.google.com/linux/chrome/deb stable InRelease              
Hit:3 http\://ppa.launchpad.net/ondrej/php/ubuntu focal InRelease           
Get:4 https\://download.opensuse.org/repositories/devel:/kubic:/libcontainers\:/stable/xUbuntu\_20.04  InRelease \[1,642 B]
Hit:5 http\://archive.ubuntu.com/ubuntu focal InRelease   
Get:6 http\://archive.ubuntu.com/ubuntu focal-updates InRelease \[114 kB]
Hit:7 http\://archive.ubuntu.com/ubuntu focal-backports InRelease       
Ign:8 https\://pkg.jenkins.io/debian-stable binary/ InRelease           
Hit:9 https\://pkg.jenkins.io/debian-stable binary/ Release
Fetched 115 kB in 4s (29.1 kB/s)
Reading package lists... Done
```

**sudo**: This command is used to execute with superuser privileges. 

**apt-get**:This is the package management command. It is used for handling packages—installing, updating, and removing them.

**update**: This command is used to update the system.

**Install Jenkins**: 
```
sudo apt-get install jenkins -y
```
**Output**:
```
vivek\@vivek-HP-EliteBook-840-G2:~$ sudo apt-get install jenkins
Reading package lists... Done
Building dependency tree   
Reading state information... Done
The following packages were automatically installed and are no longer required:
  dctrl-tools dkms libdouble-conversion3 libgsoap-2.8.91 liblzf1 libpcre2-16-0
  libqt5core5a libqt5dbus5 libqt5gui5 libqt5network5 libqt5opengl5
  libqt5printsupport5 libqt5svg5 libqt5widgets5 libqt5x11extras5
  libsdl1.2debian libvncserver1 libxcb-xinerama0 libxcb-xinput0
  qt5-gtk-platformtheme qttranslations5-l10n virtualbox-dkms
Use 'sudo apt autoremove' to remove them.
The following NEW packages will be installed:
  jenkins
0 upgraded, 1 newly installed, 0 to remove and 0 not upgraded.
Need to get 0 B/89.0 MB of archives.
After this operation, 89.6 MB of additional disk space will be used.
Selecting previously unselected package jenkins.
(Reading database ... 203565 files and directories currently installed.)
Preparing to unpack .../jenkins\_2.426.2\_all.deb ...
Unpacking jenkins (2.426.2) ...
Setting up jenkins (2.426.2) ...
Created symlink /etc/systemd/system/multi-user.target.wants/jenkins.service → /lib/systemd/system/jenkins.service.
Processing triggers for systemd (245.4-4ubuntu3.22) …
```
**sudo**: This command is used to execute with superuser privileges. 

**apt-get**:This is the package management command. It is used for handling packages—installing, updating, and removing them.

**install**: This is an argument for the apt-get command, specifying that we want to install a package.

**jenkins**: This is name of package.

* **Check Jenkins:**
```
which jenkins
```
**Output:**
```
vivek\@vivek-HP-EliteBook-840-G2:\~$ which jenkins
/usr/bin/jenkins
vivek\@vivek-HP-EliteBook-840-G2:\~$
```
**which**: This command is used to find the path.

**jenkins**: This is name of tool.

* **Check Jenkins Service:**
```
systemctl status jenkins
```
**Output:**
```
vivek\@vivek-HP-EliteBook-840-G2:\~$ sudo systemctl status jenkins
● jenkins.service - Jenkins Continuous Integration Server
  Loaded: loaded (/lib/systemd/system/jenkins.service; enabled; vendor prese>
  Active: active (running) since Sat 2023-12-30 15:10:46 IST; 2min 41s ago
   Main PID: 32522 (java)
   Tasks: 45 (limit: 9273)
  Memory: 1.6G
  CGroup: /system.slice/jenkins.service
          └─32522 /usr/bin/java -Djava.awt.headless=true -jar /usr/share/jav>
Dec 30 15:10:00 vivek-HP-EliteBook-840-G2 jenkins\[32522]: 7dca292b3cb544d38a01d>
Dec 30 15:10:00 vivek-HP-EliteBook-840-G2 jenkins\[32522]: This may also be foun>
Dec 30 15:10:46 vivek-HP-EliteBook-840-G2 jenkins\[32522]: 2023-12-30 09:40:46.0>
Dec 30 15:10:46 vivek-HP-EliteBook-840-G2 jenkins\[32522]: 2023-12-30 09:40:46.0>
Dec 30 15:10:46 vivek-HP-EliteBook-840-G2 systemd\[1]: Started Jenkins Continuou>
Dec 30 15:11:12 vivek-HP-EliteBook-840-G2 jenkins\[32522]: 2023-12-30 09:41:12.9>
Dec 30 15:11:12 vivek-HP-EliteBook-840-G2 jenkins\[32522]: 2023-12-30 09:41:12.9>
vivek\@vivek-HP-EliteBook-840-G2:\~$
```
**systemctl**: this command is used to control and query the state of the systemd system and service manager.

**status**: This is an argument or sub-command for systemctl. When used with 'systemctl' It displays the current status and some additional information about a specified service.

**jenkins**: This is the name of the service you are checking the status for.

# Access Jenkins 

* Now you can access the Jenkins web interface by opening a web browser and navigating to **http:localhost:8080** and open Jenkins with password which created when you are installing Jenkins.
  
![](https://github.com/vivekpandey1222/Jenkins-vs-Ansible/assets/151363790/b165f34b-3a5e-4c31-870e-5db82481ba5c)

* To know the password.
```
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```
**Output**:
```
vivek@vivek-HP-EliteBook-840-G2:~$ sudo cat /var/lib/jenkins/secrets/initialAdminPassword
1bfca04f83fb46fab7168b3dbfd160fb
vivek@vivek-HP-EliteBook-840-G2:~$
```
* To Unlock Jenkins page, paste this password into the **Administrator password** field and click **Continue**

![](https://github.com/vivekpandey1222/Jenkins-vs-Ansible/assets/151363790/e2006b33-accd-4000-bd35-56f1307d2e97)

* **Customizing Jenkins with plugins**

After unlocking Jenkins, costomise Jenkins page appeaars and you can click on **Install suggested plugins** or **Select plugins to install** according to your need otherwise skip it.

  # Creating the first administrator user
  
  After customizing Jenkins with plugins, Jenkins asks you to create your first administrator user.


* When the Create First Admin User page appears, specify the details for your administrator user in the respective fields and click Save and continue.
  
![](https://github.com/vivekpandey1222/Jenkins-vs-Ansible/assets/151363790/8ad4655a-b9a2-4095-b1a5-847396015f42)

* When the Jenkins is ready page appears, click Start using Jenkins.
  
![](https://github.com/vivekpandey1222/Jenkins-vs-Ansible/assets/151363790/d29f23b3-a984-44bb-ac7f-c8e516a7c474)

# Jenkins Dashboard

* Now you can see the home page of Jenkins:

![](https://github.com/vivekpandey1222/Jenkins-vs-Ansible/assets/151363790/9d3b5738-e81f-482d-a199-8f65e2313ca6)

**Configuration Panal**
* New Item
* People
* Build History
* my views
* Manage Jenkins

**New item**: Click on this option and create a new job.

![](https://github.com/vivekpandey1222/Jenkins-vs-Ansible/assets/151363790/d44c540a-5cca-46e9-8075-9aeeefa0326b)

**People**: You can see about Jenkins users.

![](https://github.com/vivekpandey1222/Jenkins-vs-Ansible/assets/151363790/1bdc6814-da93-4bf4-a204-90a6349f7ae7)

**Build history**: To see record of all the times your software project was built and tested.

![](https://github.com/vivekpandey1222/Jenkins-vs-Ansible/assets/151363790/4034b5ca-fd72-4afc-8872-2210ea513083)

**New view**: It help to orgnize the project.like- catogries job .

![](https://github.com/vivekpandey1222/Jenkins-vs-Ansible/assets/151363790/fe3c533f-6bbc-4b9d-ba9d-7825742974ed)

**Manage Jenkins**: Jenkins administrative tasks can be performed from the Manage Jenkins

![](https://github.com/vivekpandey1222/Jenkins-vs-Ansible/assets/151363790/6dfaa45d-c469-4870-9328-f2ffab7a98cb)

# Create first job 
Click on "New Item" and enter a name for job and Select the "Freestyle project" and click on "ok" then show the configuration General setting option schroll down and click on "build step" and select the "excecute shell" option and create the simple job like echo "hello world" then apply and save.
![](https://github.com/vivekpandey1222/Jenkins-vs-Ansible/assets/151363790/3b2a33cd-51b5-4d70-8400-c25979a9edba)

![](https://github.com/vivekpandey1222/Jenkins-vs-Ansible/assets/151363790/91ecf5aa-b850-4cb3-a462-cee93e7b1753)

![](https://github.com/vivekpandey1222/Jenkins-vs-Ansible/assets/151363790/5acf83e1-d5f1-414b-bb4a-bca26aa0a02c)

**Build and run the job**
Make sure have on the dashboard and click on the job name "demo7" there be a dropdown option from there select the "Build now" option.
![](https://github.com/vivekpandey1222/Jenkins-vs-Ansible/assets/151363790/6e0b7af2-b725-4573-8658-601b485e6e35)

![](https://github.com/vivekpandey1222/Jenkins-vs-Ansible/assets/151363790/2eb5d6a1-4cdb-4def-9629-533a02dc1be7)

Now click on the "demo7" and then show the left like "#1" option and click on it.
![](https://github.com/vivekpandey1222/Jenkins-vs-Ansible/assets/151363790/c22fc5ed-bf9a-4ef8-9fc1-2bac1d852460)

Show the dashboard like this.
![](https://github.com/vivekpandey1222/Jenkins-vs-Ansible/assets/151363790/6b61a259-4091-4fef-acec-bd3ec7d233ce)

Now Click on the "console output" then show the Output of echo "hello world".
![](https://github.com/vivekpandey1222/Jenkins-vs-Ansible/assets/151363790/ef13a74d-c6dc-474c-8084-887724db405f)

If you want to change the command and add on this.
Click on jobs like "demo7" dropdown and click on configure option then you can see the configuration general setting and scroll down and change on execute shell.

![](https://github.com/vivekpandey1222/Jenkins-vs-Ansible/assets/151363790/94b90576-3a4d-4a88-ad24-4fcc8ab420f4)


If you want to see the output of these command go to
terminal and follow these step.
```
cd var/lib/jenkins/
```
**Output**:
```
vivek@vivek-HP-EliteBook-840-G2:~$ cd /var/lib/jenkins/
vivek@vivek-HP-EliteBook-840-G2:/var/lib/jenkins$ ls
config.xml
hudson.model.UpdateCenter.xml
hudson.plugins.git.GitTool.xml
identity.key.enc
jenkins.install.InstallUtil.lastExecVersion
jenkins.install.UpgradeWizard.state
jenkins.model.JenkinsLocationConfiguration.xml
jenkins.plugins.git.GitHooksConfiguration.xml
jenkins.security.apitoken.ApiTokenPropertyConfiguration.xml
jenkins.security.QueueItemAuthenticatorConfiguration.xml
jenkins.security.UpdateSiteWarningsConfiguration.xml
jenkins.telemetry.Correlator.xml
jobs
logs
nodeMonitors.xml
nodes
org.jenkinsci.plugins.gitclient.GitHostKeyVerificationConfiguration.xml
org.jenkinsci.plugins.resourcedisposer.AsyncResourceDisposer.xml
plugins
queue.xml
queue.xml.bak
secret.key
secret.key.not-so-secret
secrets
updates
userContent
users
workspace
vivek@vivek-HP-EliteBook-840-G2:
```
Now go to workspace directory.

```
cd workspace
```
**Output**:
```
vivek@vivek-HP-EliteBook-840-G2:/var/lib/jenkins$ cd workspace/
vivek@vivek-HP-EliteBook-840-G2:/var/lib/jenkins/workspace$ 
```
See the all jobs name which create in jenkins dashboard.
```
vivek@vivek-HP-EliteBook-840-G2:/var/lib/jenkins/workspace$ ls
Demo  demo2  demo3  demo4  demo5  demo7
vivek@vivek-HP-EliteBook-840-G2:/var/lib/jenkins/workspace$ 
```

# Git & Github
**Git**: The Git plugin is a popular and essential tool for integrating Git repositories into your build and deployment processes. The Git plugin provides functionality to clone, fetch, and checkout Git repositories during your Jenkins jobs. 

**Github**:GitHub  is a  online storage locker for code. Developers put their code projects in these lockers, called repositories, and can easily track changes, share them with others, and work together on them.

**Configure Git in Jenkins Job**:

* In your Jenkins job configuration, under the "Source Code Management" section, select "Git".
* Enter the URL of your Git repository.
 ![](https://github.com/vivekpandey1222/Jenkins-vs-Ansible/assets/151363790/e782b14d-33c0-4f84-8844-1e7d327b0271)

* select the branch (main).
  ![](https://github.com/vivekpandey1222/Jenkins-vs-Ansible/assets/151363790/3b3c258e-d50a-4e48-aa92-f72f189e4447)

* add the command as your need in execute shell then save and apply.
* after this process now build the job and run.You can see the output click on console output.
  
 ![](https://github.com/vivekpandey1222/Jenkins-vs-Ansible/assets/151363790/b7a7e2a3-7556-4748-939c-e28528dbb892)

# Build periodically
 Build periodically in Jenkins means scheduling a job to run automatically at specific times.
* Go to the configuration page of the job you want to schedule.like-
![](https://github.com/vivekpandey1222/Jenkins-vs-Ansible/assets/151363790/e4e58869-3a51-4a7d-a3ed-e6b85434ca5d)

* Under the "Build Triggers" section, check the box for "Build periodically".
* In the "Schedule" field, enter a cron-like expression to define when the job should run.
* Shedule timing every one minutes :*/1 * * * *.
  
![](https://github.com/vivekpandey1222/Jenkins-vs-Ansible/assets/151363790/91155e0b-3d1a-4b19-b5a7-db1be01275cc)

* Now we will wait and see the autometic build job.
  
![](https://github.com/vivekpandey1222/Jenkins-vs-Ansible/assets/151363790/a605c3b1-3cdd-4242-8057-f67d6458744a)

# Poll SCM
Poll SCM is a build trigger that periodically checks a source code management (SCM) system for any changes and triggers a new build if it finds any. This is a common way to implement continuous integration (CI), where code changes are automatically integrated and tested as soon as they are pushed to the repository.

**Exa**-if I set up Poll SCM for every 2 minutes and select Git and enter the URL, then the build will check GitHub every 2 minutes to see if there is any new code. If there is new code, then the build will be triggered automatically.
* Create a new job.
* Go to configuration settings and select the git option and paste the github url.
* After go to Build trigger and click on poll scm option and set the time accoerding to need then save and apply.
 
![](https://github.com/vivekpandey1222/Jenkins-vs-Ansible/assets/151363790/b6897902-4e9a-43fb-b7b9-6216d4108ad1)

* Now you can see the result when we update the repository on guthub.

![](https://github.com/vivekpandey1222/Jenkins-vs-Ansible/assets/151363790/e9bead27-f0ae-4e1d-835e-c07ac2819a15)







</br>
</br>


# Ansible:

Ansible is an open-source automation tool that is used for configuration management, application deployment, task automation, and orchestration.Ansible uses simple, human-readable scripts called playbooks to automate your tasks.Ansible, launched in 2012 by Michael DeHaan and Red Hat acquired the ansible in 2015.

**Key Concepts and Components of Ansible**:

**Playbooks**: Ansible uses YAML-based playbooks to define automation tasks. 

**Inventory**: Ansible uses an inventory file to specify the hosts or servers it will manage. 

**Modules**: Ansible modules are reusable, standalone scripts that perform specific tasks on the managed nodes.

**Roles**: Roles provide a way to organise and structure playbooks. 

**Ansible Workflow**:

**Define Playbooks**: Write playbooks to describe the desired state of your infrastructure and the tasks needed to achieve that state.

**Inventory Setup**: Create an inventory file containing the details of the hosts you want to manage.

**Run Playbooks**: Execute playbooks using the ansible-playbook command to apply configurations and automate tasks on the specified hosts.

**Monitor and Debug**: Monitor the execution of playbooks, review logs, and debug any issues that may arise during the automation process.

**Advantage**: 
It is free for everyone.
It is very secure due to its agentless capabilities and open ssh feature.
Ansible does not need any special system administrator skill to install and use in YAML.
It is a work on  push mechanism.
It is very constrained and lightweight.


# Install Ansible:
```
sudo apt update
```
```
vivek@vivek-HP-EliteBook-840-G2:~$ sudo apt update
[sudo] password for vivek:
Ign:1 https://pkg.jenkins.io/debian-stable binary/ InRelease
Hit:2https://pkg.jenkins.io/debian-stablebinary/Release                                                                                Hit:4https://dl.google.com/linux/chrome/debstableInRelease                                                                                Hit:5http://archive.ubuntu.com/ubuntufocalInRelease                                                                                   Hit:6 http://ppa.launchpad.net/ondrej/php/ubuntu focal InRelease                                                        
Hit:7 http://security.ubuntu.com/ubuntu focal-security InRelease                                 	 
Hit:8 http://archive.ubuntu.com/ubuntu focal-updates InRelease                                  	 
Hit:9 http://archive.ubuntu.com/ubuntu focal-backports InRelease          	 
Get:10 https://download.opensuse.org/repositories/devel:/kubic:/libcontainers:/stable/xUbuntu_20.04  InRelease [1,642 B]
Fetched 1,642 B in 2s (1,041 B/s)	 
Reading package lists... Done
Building dependency tree  	 
Reading state information... Done
9 packages can be upgraded. Run 'apt list --upgradable' to see them.
vivek@vivek-HP-EliteBook-840-G2:~$
```
```
sudo apt-get install ansible
```
```
vivek@vivek-HP-EliteBook-840-G2:~$ sudo apt-get install ansible
Reading package lists... Done
Building dependency tree  	 
Reading state information... Done
ansible is already the newest version (2.9.6+dfsg-1).
The following packages were automatically installed and are no longer required:
  dctrl-tools dkms libdouble-conversion3 libgsoap-2.8.91 liblzf1 libpcre2-16-0 libqt5core5a libqt5dbus5 libqt5gui5 libqt5network5 libqt5opengl5
  libqt5printsupport5 libqt5svg5 libqt5widgets5libqt5x11extras5 libsdl1.2debian libvncserver libxcb-xinerama0 libxcb-xinput0 qt5-gtk-platformtheme
qttranslations5-l10n virtualbox-dkms
Use 'sudo apt autoremove' to remove them.
0 upgraded, 0 newly installed, 0 to remove and 9 not upgraded.
vivek@vivek-HP-EliteBook-840-G2:~$
```
```
which ansible
```
```
vivek@vivek-HP-EliteBook-840-G2:~$ which ansible
/usr/bin/ansible
vivek@vivek-HP-EliteBook-840-G2:~$
```
```
ansible --version
```
```
vivek@vivek-HP-EliteBook-840-G2:~$ ansible --version
ansible 2.9.6
  config file = /etc/ansible/ansible.cfg
  configured module search path = ['/home/vivek/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /usr/lib/python3/dist-packages/ansible
  executable location = /usr/bin/ansible
  python version = 3.8.10 (default, Nov 22 2023, 10:22:35) [GCC 9.4.0]
vivek@vivek-HP-EliteBook-840-G
```

# Testing Ansible Playbook:

**Create an inventory file and  add the hostname**
```
touch inventory.ini
```
Open with text editor “vim” and add the hostname which you want to manage.
```
vim inventory.ini
```
![](https://github.com/vivekpandey1222/Jenkins-vs-Ansible/assets/151363790/f2b6c498-1c01-413f-aef4-fd1470474e78)

Create the simple playbook and run:
```
vim simple.yml
```
![](https://github.com/vivekpandey1222/Jenkins-vs-Ansible/assets/151363790/f8dc8a9a-e6ad-4872-8442-5673221a27ad)

**Vim**: vim is a text editor.

**---**:It denotes the start of a YAML document.

**- name**: “simple ansible test” This is the start of an Ansible play.

**host**: “localhost”Specifies the target host or group for this play.

**Task**: This is the start of the list of tasks to be executed in the play.

**- name**: Print a message: Begins the definition of a task named "Print a message."

**msg**: "Hello, this is a simple Ansible test!": Specifies the message to be printed to the console during the execution of this task.

**Now run the yml file**:
```
ansible-playbook -i inventory.ini simple.yml
```
![](https://github.com/vivekpandey1222/Jenkins-vs-Ansible/assets/151363790/7a8a70a0-92b4-4638-9d89-ed0c36e27f8f)


**ansible-playbook**:This is the command used to run Ansible playbooks.

**-i inventory.ini**: This option specifies the inventory file to use.

**Simple.yml**: This is the name of the yml file name.
