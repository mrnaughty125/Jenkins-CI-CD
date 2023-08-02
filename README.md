
<h1>Continuous Integration and Continuous Deployment (CI/CD) with Jenkins and HTTPD</h1>

<h2>1. Create an EC2 Instance using Amazon Linux OS</h2>
<p>Allow all traffic from anywhere in the network.</p>

<h2>2. Connect to the Instance</h2>
<p>Execute the following commands:</p>

<ul>
    <li>sudo yum update</li>
    <li>sudo -i (Switch to the root user)</li>
    <li>sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo</li>
    <li>sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key</li>
    <li>amazon-linux-extras install java-openjdk11</li>
    <li>java --version</li>
    <li>yum install jenkins -y</li>
    <li>systemctl enable jenkins</li>
    <li>systemctl start jenkins</li>
    <li>systemctl status jenkins</li>
</ul>

<h3>3. Access Jenkins</h3>
<p>To access Jenkins, use the Public IP followed by port 8080.</p>

<h3>4. Jenkins Initial Admin Password</h3>
<p>To retrieve the initial admin password for Jenkins:</p>
<ul>
    <li>cat /var/lib/jenkins/secrets/initialAdminPassword</li>
</ul>

<h3>5. Install Suggested Plugins and Create a Job</h3>
<p>Install the suggested plugins and create a FreeStyle project.</p>

<h3>6. Configure Instance for Deployment</h3>
<p>Go back to the instance and install Git and HTTPD:</p>
<ul>
    <li>yum install git -y</li>
    <li>yum install httpd -y</li>
    <li>systemctl enable httpd</li>
    <li>systemctl start httpd</li>
    <li>systemctl status httpd</li>
</ul>

<h2>*** Make sure HTTPD status is running ***</h2>

<h3>7. Configure CI/CD</h3>
<p>Make necessary build configurations and create a build again.</p>

<h3>8. Set Up Auto Build</h3>
<p>
To enable automatic builds on changes in GitHub:
<br>
- Use the "Poll SCM" option in Jenkins configuration.
<br>
- Make changes to the GitHub code, and Jenkins will automatically trigger the build after one minute due to the * * * * * cron schedule.
<br>
- Observe the changes on the website after the auto build.
</p>
