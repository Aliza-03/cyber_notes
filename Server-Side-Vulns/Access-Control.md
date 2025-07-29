# Basics of Access Control

## What is Access Control?

Access Control can be defined on how an application may restrict or allow the use of certain functionalities or access certain resources based on the type of user.
In web applications, access control is dependent on session management and authentication.

**Vertical Priviliege Escalation** is when an underpriviliged user gains access to priviliges they previously had no access to. **Example**: If a non administrative user gains access to deleting other user accounts, then this would be considered vertical provilige escalation.

**Horizontal Privilige Escalation** is when an attacker gains access to another user's specific information or resources with the same access rights and priviliges.

**Unprotected Functionality** occurs when sensitive functionality can be accessed by an attacker simply through browsing to the relevant URL which has no protections in place

## How to recognise?

- Sometimes the robots.txt may disclose such sensitive urls
- In certain cases, the sensitive url may be concealed with an unpredictable name. Also known as "security by obscurity", it attempts to hide the url. But that is not always effective as it may appear in for example, a JavaScript Construct.
- Some applications may store user sensitive information in user-controllable locations such as
        -> a hidden field
        -> a cookie
        -> a preset string query parameter within the url. Example url - https://example.com/admin/dashboard?role=admin
        
- Through IDOR (Insecure Direct Object Reference) vulnerabilities,  user-controller parameter values are used to access resources or functions directly.


