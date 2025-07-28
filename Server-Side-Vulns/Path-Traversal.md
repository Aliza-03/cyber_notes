# Basics of Reading Arbitrary Files via Path Traversal

## What is a Path Traversal Vulnerability

Allows an attacker to access files from the server's filesystem through sending requests via the website's URL

**Example URL taken from PortSwigger : https://insecure-website.com/loadImage?filename=../../../etc/passwd**
In this usecase, the attacker is accessing the passwd file which may contain the passwords of user's logged into the application. Note that the "../" sequence allows step ups to the filesystem root. Both "../" and "..\" are valid sequences in a Windows system

## How to identify it?

- Inspect HTTP Requests. Burpsuite is a great tool to use
- Look for filename and path parameters. If unprotected, can be exploited
- Test for filepath manipulation

## How to prevent it?

The best possible way to prevent file path traversals is to completely prevent user supplied input into filesystem APIs. An example would be to map filenames to tokens/ids or whitelisting.
If passing user-supplied input to filesystem APIs cannot be avoided PortSwigger recommends using two layers of defense to prevent attacks:

Validate the user input before processing it. Ideally, compare the user input with a whitelist of permitted values. If that isn't possible, verify that the input contains only permitted content, such as alphanumeric characters only.
After validating the supplied input, append the input to the base directory and use a platform filesystem API to canonicalize the path. Verify that the canonicalized path starts with the expected base directory.