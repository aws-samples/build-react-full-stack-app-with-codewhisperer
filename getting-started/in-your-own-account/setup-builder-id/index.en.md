---
title : "Setup Builder Id"
weight : 18
---

In this section, we will set up CodeWhisperer in VScode using an AWS Builder ID, which is a new personal profile for everyone who builds on AWS.

First we need to ensure we have the AWS Toolkit installed.

1. Navigate to Extensions on the left hand pane of your VScode IDE. In the search bar enter AWS Toolkit and click Install the extension as shown below.
![AWSToolkit Setup](/static/AWStoolkit.png)

2. There should now be an AWS Toolkit icon on the left hand pane. In the AWS Toolkit for Visual Studio Code, under Developer tools, CodeWhisperer select Start. A dropdown menu will appear at the top of VSCode.
![AWSToolkit Setup](/static/CWstart.png)

3. From the dropdown menu, select Use a personal email to sign up and sign in with AWS Builder ID
![Builder ID Setup](/static/CWBuilderID.png)

4. At the prompt Copy Code for AWS Builder ID choose Copy Code and Proceed.

5. At the prompt Do you want Code to open the external website?. Choose Open.

6. A browser tab will open, displaying the Authorize request window. The code should have been already added to your copy/paste buffer. Paste it in, and choose Next.

7. A browser tab will open to the Create AWS Builder ID page. Enter your email address, and choose Next.

8. A field for Your name will appear. Enter your name and choose Next.

9. AWS will send an confirmation code to the email address that you submitted. On the email verification screen, enter the code and choose Verify.

10. On the Choose your password screen, enter a password, confirm it, and choose Create AWS Builder ID.

11. A browser tab will open with a message asking you to allow AWS Toolkit for Visual Studio Code to access your data. Choose Allow.

12. Return to VSCode. If you have already authenticated into other AWS tools using IAM, you will be asked whether you want to use Builder ID for all AWS services. Choose the option that best suits your situation.

If you're not sure what to do, choose Yes, keep using AWS Builder ID with CodeWhisperer while using....