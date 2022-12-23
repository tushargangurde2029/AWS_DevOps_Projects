# Deploy Docker Docker Provision Django Application On AWS with Default Server & Include CI/CD with Jenkins

## Pre-requisities:

* AWS Account
* GitHub Account
* Basic Knowledge about Docker & Jenkins

### Steps:-

#### 1. Clone the Django TODO App
#### 2. Launch an EC2 Ubuntu Instance with access of HTTP & HTTPS
#### 3. Install Jenkins on Ubuntu Machine
#### 4. Setup Jenkins & Connect with GIT by Installing Github Integration
#### 5. Finally Enable the Jenkins Script for CI/CD of Docker Provision Django Application


### Step 1:

Clone the Django TODO app by running below command & push that code to your Personal Repository

```
git clone https://github.com/tushargangurde2029/django-todo.git
```

Note: You need to push this application to your personal repository so you can add SSH keys & add webhooks to implement CI/CD Integration.


### Step 2:

Go to your AWS Account & Launch an Ubuntu Instance
Open EC2 -> Instances --> Launch an EC2 Instance
Select Ubuntu Image


Provide Following Details
Name = SampleDjangoApp
Instance Type = t2.micro
Allow HTTP & HTTPS Traffic From Internet

Once Done Launch Your EC2 Instance

Note: Please Create a new key pair or use existing one to login


### Step 3: 

Connect to your EC2 Instance to Install Jenkins 
Run below Commands One by One

Update Your System
```
sudo apt update
```

Install JAVA
```
sudo apt install openjdk-11-jre
```

Check JAVA Version by running below command
```
java -version
```

Now Install Jenkins

```
curl -fsSL https://pkg.jenkins.io/debian/jenkins.io.key | sudo tee \   /usr/share/keyrings/jenkins-keyring.asc > /dev/null
```

```
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \   https://pkg.jenkins.io/debian binary/ | sudo tee \   /etc/apt/sources.list.d/jenkins.list > /dev/null
```


```
sudo apt-get update 
```


```
sudo apt-get install jenkins
```


Once Done Enable & Start the Jenkins Service


```
sudo systemctl enable jenkins
```

Starts the Jenkins Service
```
sudo systemctl start jenkins
```

Check the Service Status
```
sudo systemctl status jenkins
```
