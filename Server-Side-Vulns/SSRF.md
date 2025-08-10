# Server Side Request Forgery

## What is SSRF?
Server-side request forgery is a web security vulnerability that allows an attacker to cause the server-side application to make requests to an unintended location.

In a typical SSRF attack, the attacker might cause the server to make a connection to internal-only services within the organization's infrastructure. In other cases, they may be able to force the server to connect to arbitrary external systems. This could leak sensitive data, such as authorization credentials.

In some cases, the application server is able to interact with back-end systems that are not directly reachable by users. These systems often have non-routable private IP addresses. The back-end systems are normally protected by the network topology, so they often have a weaker security posture. In many cases, internal back-end systems contain sensitive functionality that can be accessed without authentication by anyone who is able to interact with the systems.

## How to recognise?
Look for parameters that:

 - Accept full URLs (url=, link=, target=, redirect=, callback=, webhook=)
 - Are used in features like:
 - Importing/fetching data
 - File/image preview or download
 - Webhooks or callbacks
 - API proxy
 - When changed, the server fetches from that location


Test with:
- External URL you control → see if server requests it
- Internal URL like http://127.0.0.1 or http://169.254.169.254 and see if internal data comes back