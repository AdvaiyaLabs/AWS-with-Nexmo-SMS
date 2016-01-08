# AWS with Nexmo SMS
<img src="https://github.com/AdvaiyaLabs/AWS-with-Nexmo-SMS/blob/master/docs/image1.jpeg" width="200">
## Introduction
For system-wide visibility into AWS cloud resources and applications, user can leverage AWS messaging and monitoring services such as AWS Simple Notification Services (SNS) and AWS CloudWatch to get notification for critical events such as CPU usage, Disk usage, application performance etc. To receive such notifications as SMS on mobile, user can use the AWS with [Nexmo SMS](https://ww.nexmo.com/sms) app that makes it easy to set up, operate, and send notifications from the AWS cloud. This app collects published messages from AWS service such as AWS SNS and immediately deliver them to subscriber’s mobile as SMS.

AWS with [Nexmo SMS](https://ww.nexmo.com/sms) is a web service which sends SMS using the [Nexmo Messaging APIs](https://docs.nexmo.com/api-ref/sms-api). This service communicates with AWS SNS service and sends SMS notification to the configured phone number whenever the defined condition satisfies.

## Use Case
For AWS cloud resources and applications, enable AWS Administrator to receive real-time SMS notifications wherever they are.

## Prerequisites 
 - Python 2.7
 - AWS user with administrative privileges
 - Nexmo subscription and corresponding Nexmo API keys (Keys and Secret). To access the API keys, see appendix section.
 
## Features
 - Enable and disable SMS functionality
 - Send AWS notifications as SMS
 - Easy integration and configuration with SNS
 - User friendly UI
 - Real time notification 
 - It supports Ubuntu operating systems (OS)
 - Compatible with any AWS service which is mapped to AWS SNS

## Steps to deploy the AWS with Nexmo SMS
To install the AWS with Nexmo SMS app on Ubuntu, follow the below steps:

1.	Go to AWS Instance terminal ie. Putty or SSH
2.	Clone the AWS with Nexmo SMS repository use the following commands.

	**```cd ~```** 
	
	**```sudo apt-get install git```** 
	
	**```git clone https://github.com/AdvaiyaLabs/AWS-with-Nexmo-SMS.git```**
	
3.	Change the directory to the AWS with [Nexmo SMS](https://ww.nexmo.com/sms).

	**```cd AWS-with-Nexmo-SMS```**
4.	Run the following command to install and configure the Nexmo services.

	**```sudo python install.py```**

	 
	This will install the following on AWS instance:
	 - Django 1.8.5
	 - Nexmo library
	 - Python 2.7
 
 
## AWS security settings
1.	Login to the AWS Web Console.
2.	Select EC2 Service.
3.	On EC2 dashboard, select the EC2 instance where you have installed the **AWS with Nexmo SMS** app. 
4.	Click on the **Security groups** link as shown in the image below:
	
	<img src="https://github.com/AdvaiyaLabs/AWS-with-Nexmo-SMS/blob/master/docs/image4.png" width=600>
5.  Select **Inbound** and click on **Edit** as shown in the image below.
	
	<img src="https://github.com/AdvaiyaLabs/AWS-with-Nexmo-SMS/blob/master/docs/image5.png" width=600>
6.	In the popup, click on **Add Rule** to define the rule to access on internet.
7.	Select the **Custom TCP Rule,** and set the port number as **9033** and set source as **0.0.0.0/0** or specific IP to access internet as shown in the below image:
	
	<img src="https://github.com/AdvaiyaLabs/AWS-with-Nexmo-SMS/blob/master/docs/image6.png" width=600>
8. Click on **Save**

## Steps to use the AWS with Nexmo SMS
1.  Go to the browser and type **&lt;&lt;AWS Instance IP&gt;&gt;:9033** (replace AWS Instance IP with your instance public IP address).
2.  Login with default credentials - username: **admin** and password: **admin.**
3.  Click on **Login**.
	
	<img src="https://github.com/AdvaiyaLabs/AWS-with-Nexmo-SMS/blob/master/docs/image7.png" width=400>
	
4.	Set the value according to the label shown. To get the Nexmo API key and secret key, see the appendix. To receive SMS from the Nexmo, check **Enable SMS**.

	<img src="https://github.com/AdvaiyaLabs/AWS-with-Nexmo-SMS/blob/master/docs/image8.png" height=600>
5.  Click on **Save**.

## Steps to configure SNS on AWS
1.	Login to the AWS Web Console.
2.	Select the **SNS** services from the menu.
	
	<img src="https://github.com/AdvaiyaLabs/AWS-with-Nexmo-SMS/blob/master/docs/image9.png" width=600>
3.	Click on the **Create Topic**.
	
	<img src="https://github.com/AdvaiyaLabs/AWS-with-Nexmo-SMS/blob/master/docs/image10.png" width=400>
4.  Type the **Topic name** and **Display name**. Click on **Create topic**.
	
	<img src="https://github.com/AdvaiyaLabs/AWS-with-Nexmo-SMS/blob/master/docs/image11.png" width=600>
5.  Click on **Create Subscription**.

	<img src="https://github.com/AdvaiyaLabs/AWS-with-Nexmo-SMS/blob/master/docs/image12.png" width=600>
6.  Enter the **Topic ARN**, **Protocol** and set **Endpoint** **&lt;&lt;AWS\_public\_ip&gt;&gt;:9033** as shown in the below image:
	
	<img src="https://github.com/AdvaiyaLabs/AWS-with-Nexmo-SMS/blob/master/docs/image13.png" width=600>
7.  Click on **Create Subscription.**

## Configure Notification on AWS Cloudwatch
1.  Select the **CloudWatch** service from the Menu.

	<img src="https://github.com/AdvaiyaLabs/AWS-with-Nexmo-SMS/blob/master/docs/image14.png" width=400> 
2.  Click on the **Browse Metrics**.

	<img src="https://github.com/AdvaiyaLabs/AWS-with-Nexmo-SMS/blob/master/docs/image15.png" width=600>
3.  Select the metrics to monitor, for example - click on **Per-Instance Metrics**.
4.  Select the metrics on which you want to set alarm.
5.  Click on **Create Alarm**.

	<img src="https://github.com/AdvaiyaLabs/AWS-with-Nexmo-SMS/blob/master/docs/image16.png" width=600>
6.  **Create Alarm** window will open. Perform the following steps:
	
	<img src="https://github.com/AdvaiyaLabs/AWS-with-Nexmo-SMS/blob/master/docs/image17.png" width=600>
    
	1.	Set the threshold to raise notification
	2.	Select topic from the **Send notification to** drop down menu
	3.	Click on **Create Alarm**
7.	SMS will be received on the satisfaction of the condition.


Appendix
========

Get Nexmo API Keys
------------------

- To access Nexmo keys, go to https://www.nexmo.com/ and Sign-in 
- On the top right corner, click on the **Api Settings** 
- Key and Secret will display in the top bar as shown in the below image:
	![](https://github.com/AdvaiyaLabs/AWS-with-Nexmo-SMS/blob/master/docs/image18.jpeg) 