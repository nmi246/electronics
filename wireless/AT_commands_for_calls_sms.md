AT commands for Calls, SMS, call forwarding, etc. 


NOTE: some commands may be module specific. To avoid problems, ensure you're using the correct AT command manual.


AT commands manual for: LARA-L6 / LARA-R6 series Single or multi-mode LTE Cat 4 / LTE Cat 1 modules with Secure Cloud
https://content.u-blox.com/sites/default/files/LARA-R6_ATCommands_UBX-21046719.pdf

Check status, network info, device IMEI, RAT (2G, 3G, 4G, 5G) , etc. 
ATI9
ATI3
AT!GSTATUS?

AT+CPWROFF - power off

AT+CFUN=0 - tx/rx off
AT+CFUN=1 - tx/rx on


Sending and Receiving voice calls:
- ATD0220974881 - send a voice call
- ATD0220974881,2 - send a voice call to a number with extension = 2
- ATA - pick up receiving call
- ATH - Halt/decline/stop incoming or outgoing call
- ATC+CLCC - check active call (shows phone number of current person/device you're calling)


## Sending and Receiving SMS text messages:
- AT +CMGF = 1
- AT+CMGS="0220974881"  - send SMS text message. When finished writing Message termintate text message with CTRL+Z
- AT+CMGR = 39 ?? read SMS send to your device??
- AT+CMGR = 24 ?? 


## Change RAT (radio access network):
- AT+KSRAT=2 --> Lock to 3G only
- AT+KSRAT=5 --> Lock to 4G only
- AT+KSRAT=0 --> Auto select



## Call forwarding setup:
Vodafone call forwarding instructions: https://www.vodafone.co.nz/faq/forward-a-call-from-your-mobile
- ATD\**21*0220974881# - Call forwarding from mobile phone (e.g., iPhone)
- AT+CCFC=0,3,"phone number"
- AT+CCFC=0,3,"+64220974881",145  - forward receiving calls to +64220974881 (interntional PH# format)
- AT+CCFC=0,3,"0220974881" - forward receiving calls to 0220974881 (local PH# format)
 

## Call barring:
Block incoming/outgoing calls, Vodafone: https://www.vodafone.co.nz/faq/block-incoming-or-outgoing-calls-on-your-mobile
- image from iPhone:
  -  ![image](https://user-images.githubusercontent.com/42329930/233904746-02ccc959-e554-4812-afc1-c8fe475b2723.png)


## Call waiting:
- AT+CCWA?
- AT+CCWA = 0 - disable call waiting??
- AT+CCWA = 1 - enable call waiting ?? 
- AT+CHLD = 2 ?? hold call 1, go on call 2??
- - AT+CHLD = 1 ?? hold call 2, go to call 1?
- - AT+CHLD = 3 ??



AT+CNUM - ??
AT+WDDM - ??
AT+VTS=5 - ??
AT+VTS=4 - ??








