ul.{
	 list-style-type: square;
} 

<h1>CI-CD THROUGH JENKINS USING HTTPD</h1>

<h3>CREATE AN EC2 INSTANCE USING AMAZON LINUX OS BY ALLOWING ALL TRAFFIC AND ANYWHERE IN NETWORK</h3>

<h3>
<p>
Connect the instance<br>
Excute the following commands<p>
</h3>


<ul>
<li>sudo yum update</li>
<li>sudo -i ( For switching into root user )</li>
<li>sudo wget -O /etc/yum.repos.d/jenkins.repo \ https://pkg.jenkins.io/redhat-stable/jenkins.repo</li>
<li>sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key</li>
<li>amazon-linux-extras install java-openjdk11</li>
<li>java --version</li>
<li> yum install jenkins -y</li>
<li>systemctl enable Jenkins</li>
<li>systemctl start Jenkins</li>
<li>systemctl status Jenkins</li>
</ul>
  
  
   
  


   
<ul>TO CONNECT THE JENKINS USE PUBLIC IP:8080</ul>
<h2>For password<h2> 
<ul>
<li>cat /var/lib/jenkins/secrets/initialAdminPassword</li>
</ul>
 
<h3><p>
INSTALL SUGGESTED PLUGINS<br>
CREATE A JOB <br>
CREATE USING FREE STYLE PROJECT<br>
</p>
</h3>

 
<h3>GO BACK TO INSTANCE AGAIN AND INSTALL GIT AND HTTPD</h3>


<ul>
<li>yum install git -y<li>
<li>yum install httpd -y<li>
<li>systemctl enable httpd<li>
<li>systemctl  start httpd<li>
<li>systemctl status httpd<li>
<ul>

*** make sure status is running 

  
  
  
AGAIN TO CONFIGURE 
 
 
MAKE A BULID AGAIN 
 

For auto bulid in the change in github using POLL-SCM 
Again go to configure and make some additions
 
Build again once and see any errors
 
 

Before change in github the website looks :
 

Lets make some change in git hub code the next build will perform automatically hence the CD performed here for CI.
  
The auto build is done after one minute because the poll scm is * * * * * it means for  change of the code in github after one minute it reflects to the website.

The change in website after auto bulid:
 
