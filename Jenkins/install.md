# Linux 

Jenkins installers are available for several Linux distributions.

Debian/Ubuntu

$ sudo apt update
$ sudo apt install openjdk-11-jre
$ java -version
openjdk version "11.0.12" 2021-07-20
OpenJDK Runtime Environment (build 11.0.12+7-post-Debian-2)
OpenJDK 64-Bit Server VM (build 11.0.12+7-post-Debian-2, mixed mode, sharing)



Start Jenkins
You can enable the Jenkins service to start at boot with the command:


sudo systemctl enable jenkins


sudo systemctl start jenkins


sudo systemctl status jenkins
