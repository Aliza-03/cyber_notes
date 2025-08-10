# Basics of File Upload

## What is file upload vulnerability?
File upload vulnerabilities are when a web server allows users to upload files to its filesystem without properly placing validation checks for
- file name
- file type
- file contents
- file size 

This can result in malicious files to be uploaded by the attacker containing script files enabling remote code execution.
From a security perspective, the worst possible scenario is when a website allows you to upload server-side scripts, such as PHP, Java, or Python files, and is also configured to execute them as code. This can allow for a successful creation of your own webshell in the server.
