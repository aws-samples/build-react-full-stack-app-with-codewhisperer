---
title : "Configure your IDE"
weight : 14
---



As a reminder, CodeWhisperer integrates with multiple IDEs—including JetBrains, Visual Studio Code, AWS Cloud9, and the AWS Lambda console— and currently supports C#, Java, JavaScript, Python, and TypeScript..

In this workshop we will be using Visual Studio Code. In order to get to the hands-on-keyboard portion of the workshop as quickly as possible, we will be using Visual Studio via code-server, hosted on an Amazon EC2 Instance.

### Accessing code-server
1. First we will access the code server we will use for the duration of the workshop. Please navigate to the [Workshop Studio Event Outputs](https://catalog.us-east-1.prod.workshops.aws/event/dashboard/en-US) .
2. Once there, scroll down until you see the Event Outputs at the bottom of the page.
3. Copy the cfn-VSCodeWebUrl value (the URL) and paste it into your web browser as shown below.
![Code server](/static/CodeserverURL.png)

4. Now, you will be prompted to enter a password. Navigate back to the [Workshop Studio Event Outputs](https://catalog.us-east-1.prod.workshops.aws/event/dashboard/en-US)  again and copy the Password value and paste it into the prompt on the code-server as shown below.
![Submit](/static/submit.png)

5. Click Submit. You should now see the VSCode IDE as shown below.
![VS Code Server](/static/VScodeserver.png)

6. Now, open a new terminal by clicking the icon in the top left corner and navigating to Terminal -> New Terminal as shown below.
![New Terminal](/static/NewTerminal.png) 

::alert[Follow the instructions in this section if you intend to use VScode hosted web client or have restrictions preventing you from using the desktop version.]{header="Note"}



