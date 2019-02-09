# Install Git
```sh
$sudo yum -y update
$sudo yum install git
```

#Install Jenkins
```sh
#Jenkins needs JDK1.8 but AMI has JDK1.7 pre-installed
#Install JDK1.8 and remove JDK1.7
$sudo yum install java-1.8.0
$sudo yum remove java-1.7.0-openjdk

#Add Jenkins Repo so that Yum knows where to pull+Install Jenkins from 
$sudo wget -O /etc/yum.repos.d/jenkins.repo http://pkg.jenkins-ci.org/redhat/jenkins.repo

#Add Jenkins GPG Key to Trusted keystore
$sudo rpm --import http://pkg.jenkins-ci.org/redhat/jenkins-ci.org.key

$sudo yum install jenkins

#To ensure that Jenkins starts evertime your EC2 instance starts
$sudo chkconfig --add jenkins
```
