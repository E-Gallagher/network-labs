# Lab 002: Troubleshooting (Two subnets routed by one router)

## Incident 1: Wrong default gateway on PC0

### Symptom
Using the working baseline from Lab 001, PC0 could ping its gateway (192.168.10.1) but could not ping PC1 (192.168.20.10).  
Evidence: evidence/inc1-before.png

### Cause
Links were up (green). PC0’s default gateway was set to 192.168.10.254.  
Since 192.168.20.10 is off-subnet, PC0 must send that traffic to the default gateway, and the wrong gateway meant the traffic went nowhere.

### Fix
Set PC0 default gateway back to 192.168.10.1.

### Proof
PC0 could ping 192.168.20.10 again.  
Evidence: evidence/inc1-after.png

---

## Incident 2: Router G0/1 shutdown

### Symptom
PC0 could not ping PC1 (192.168.20.10).

### Cause
On the router, `show ip interface brief` showed GigabitEthernet0/1 was **administratively down**.  
Evidence: evidence/inc2-down.png

### Fix
Bring the interface back up:
```text
configure terminal
interface gigabitEthernet0/1
no shutdown
end



