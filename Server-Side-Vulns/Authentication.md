# Basics of Authentication Vulnerability

## What are they?
Authentication vulnerabilities can allow attackers to gain access to sensitive data and functionality. They also expose additional attack surface for further exploits. 

**KeyNote**: Authentication is the verification of an identity whereas Authorization involves the scope of allowed activities to an authenticated user.

### Attacks to Authentication

#### Brute Force Attacks
The use of trial and error to guess a user's credentials. These type of attacks tend to be automated using pre-existing wordlists from previously leaked passwords and dedicated tools.

#### Bypassing Two-Factor Authentication
The flawed and incomplete use of two factor authentication means that after completeing the first step, the user is essentially in a "logged in" state. This means in certain cases, the attacker can skip step two entirely and bypass two factor authentication since the website doesn't check if both steps have been completed.

### Prevention

- Ensure the use of complicated, strong passwords
- Store passwords in a hash format
- Ensure proper implementation of two factor authentication
