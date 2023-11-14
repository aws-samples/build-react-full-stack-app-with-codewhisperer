## Run Security Scan


Run Security Scan performs a security scan on currently active file in the IDE editor, and its dependent files from the project. After the scan is finished, security issues in the scanned files are highlighted in the Problems panel in VSC. Note that for JetBrains, security issues are highlighted in a separate CodeWhisperer Security Issues tab in the Problems panel.

CodeWhisperer's security scan is integrated with Amazon CodeGuru. CodeGuru does multiple layers of filtering before scanning code to ensure that you can focus on the most critical issues. As part of that, CodeGuru filters unsupported languages, and also tests code, including open source code, before scanning for security issues.

To begin a security scan in VS Code, use the following procedure.

1. In VS Code, choose the AWS logo on the left side of the window. The AWS Toolkit panel will open.

2. In the AWS Toolkit panel, under Developer Tools, under CodeWhisperer, choose Start Security Scan.

3. You will find security vulnerability in your code
![security scan](/static/securityscanreport.png)

4. You can click on security finding and it will navigate to vulnerable script.
![security scan](/static/securityscanreport1.png)

Congratulations! Its time to appreciate youself and realize how fast you were to build a functional fullstack React application & aware of all security issue in your code even before commiting in your source control.

### 📁 Next: [Summary](/summary/index.en.md)