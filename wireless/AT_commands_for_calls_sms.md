AT commands for Calls, SMS, call forwarding, etc. 


NOTE: some commands may be module specific. To avoid problems, ensure you're using the correct AT command manual.


AT commands manual for: LARA-L6 / LARA-R6 series Single or multi-mode LTE Cat 4 / LTE Cat 1 modules with Secure Cloud
https://content.u-blox.com/sites/default/files/LARA-R6_ATCommands_UBX-21046719.pdf

Check status, network info, device IMEI, RAT (2G, 3G, 4G, 5G) , etc. 
- ATI9
- ATI3
- AT!GSTATUS?
- AT+CCID
- AT+CIMI
- AT!OPENLOCK? - unlock level 3 security ??
- at!unlock="A710"                                             //unlock level 3 security
More on this:
- ATI
- ATI8
- ATI9
- AT!SKU?
- AT!PRIID?
- AT!PACKAGE?
- AT+COPS?
- AT!SELRAT?
- AT!BAND?
- AT+CGDCONT?
- at!gstatus
- at+cscs="GSM"
- at+cscs?
- at+cusd=1,"*33*0000#",15  // Enable call barring
- AT!ENTERCND="A710"        //unlock level __ security


## MISC:
- at!fmpath=/nv/item_files/modem/mmode
-at!fmr?sms_domain_pref
- !FMR: sms_domain_pref read                                 //NV item for SMS over IMS is set disabled
- at!fmw=sms_domain_pref,0,1                                 //Enabled SMS over IMS
- at!fmr?sms_domain_pref                                     //Recheck
- at!reset                                                   //Reset to take effect


AT+CPWROFF - power off

AT+CFUN=0 - tx/rx off
AT+CFUN=1 - tx/rx on


## Send and Receive voice calls:
- ATD0220974881 - make a voice call
  - AT+VTS=DTMF    # send indivual characters for selecting various options. (DTMF: 0-9, #, *, A-D)
    - e.g.: AT+VTS=1
- ATD0220974881,2 - send a voice call to a number with extension = 2
- ATA - pick up receiving call
- ATH - Halt/decline/stop incoming or outgoing call
- ATC+CLCC - check active call (shows phone number of current person/device you're calling)

## Private call, hide caller ID: (tested on Vodafone NZ network only)
- Permanent(?) solution: Using your phone’s keypad, hide your number by dialling #31# or show your number by dialling *31#, then enter the number you want to call.
- One off solution: Dial #31# and then the number you're dialing (for example #31# 021 234 567). This suppresses your Caller ID for that call, and then returns to normal.
  - example: ATD#31#0220974881;  # hides caller ID for this particular call only.    

## Sending and Receiving SMS text messages:
- AT+CMGF=1      # Indicates to the MT which input/output format of messages shall be used. 1 = text mode. 0 = PDU mode (default).
  - make sure AT+CMGF=1 before sending messages. 
- AT+CMGS="0220974881"    # **send** SMS text message. When finished writing Message termintate text message with CTRL+Z
- AT+CMGR=n               # **read** the text message stored at index n.
  - example: AT+CMGR=5    # reads the message at index 5. 
- The +CMT URC is issued on the reception of an SMS messages.
- List messages:
  - AT+CMGL="ALL"    # lists all messages.
    - AT+CMGL=?      # list all options: ("REC UNREAD","REC READ","STO UNSENT","STO SENT","ALL")
- Delete message:
  - AT+CMGD=n               # delete message stored at index n. (0-9 on RC7620). 
    - example: AT+CMGD=5    # delete message at index=5.   
  - AT+CMGD=?               # shows all the index available, and the delete options (e.g., delete only unread, etc.).  


## Change RAT (radio access network):
- AT+KSRAT=1 --> Lock to 2G (GSM only)
- AT+KSRAT=2 --> Lock to 3G (UMTS only)
- AT+KSRAT=5 --> Lock to 4G (LTE only)
- AT+KSRAT=0 --> All RATs, auto select



## Call forwarding setup:
Vodafone call forwarding instructions: https://www.vodafone.co.nz/faq/forward-a-call-from-your-mobile
- ATD\**21*0220974881# - Call forwarding from mobile phone (e.g., iPhone)
- AT+CCFC=0,3,"phone number"
- AT+CCFC=0,3,"+64220974881",145  - forward receiving calls to +64220974881 (interntional PH# format)
- AT+CCFC=0,3,"0220974881" - forward receiving calls to 0220974881 (local PH# format)
- AT+CCFC=2,2           # query status
- AT+CCFC=4,0           # all call barring, disable

 

## Call Barring from iPhone (on Vodafone network):
Block incoming/outgoing calls, Vodafone: https://www.vodafone.co.nz/faq/block-incoming-or-outgoing-calls-on-your-mobile
- image from iPhone:
  -  ![image](https://user-images.githubusercontent.com/42329930/233904746-02ccc959-e554-4812-afc1-c8fe475b2723.png)


## Call Barring from Sierra Wireless RC7620 module (on Vodafone network):
- AT+CLCK="AI",2		           # check status. If call barring is not active, response will be: +CLCK: 0,255
- AT+clck="AI",1,"0000"	     # Enable call barring. Password is either "0000" or "1234"
- AT+CLCK="AI",2		           # Check status: If call barring is active, response will be: +CLCK: 1,1
  - If active: Incoming/outgoing calls should be disabled.   
- AT+CLCK="AI",0,"1234"	     # Disable call barring
- AT+CLCK="AI",2		           # Check status. If call barring is disabled, response will be: +CLCK: 0,255
  - Incoming/outgoing calls should be enabled.   

NB: Use "AO" for OUTGOING call barring, and "AI" for INCOMING call barring

## Call waiting, holding, conferencing:
- AT+CCWA?         # check if call waiting is enabled: 0=disabled, 1=enabled. 
- AT+CCWA=0      # disable call waiting
- AT+CCWA=1      # enable call waiting 
- AT+CHLD=2      # places all active calls (if exist) on hold and accepts the other call (held or waiting, if exist)
- AT+CHLD=3      # adds a held call to the conversation; call conferencing.
- AT+CHLD=?      # lists all supported options. 

## Listen to voice mail, and setup voice mail:
- ATD021700700;  # calling this number (specific to Vodafone NZ) will ask you to set up voice mail.
- ATD021700700;  # the voice mail number for vodafone. 
  - AT+VTS=DTMF    # send indivual characters for selecting various options. (DTMF: 0-9, #, *, A-D)
    - e.g.: AT+VTS=1
- ATD1;          # number for calling voice mail on Ublox modems (if supported)


## Set Voicemail Number (example):
set: AT+CSVM=1,"+1234567890",145
read: AT+CSVM?  # check if voice mail is setup, and what the voicemail number is.
cancel voicemail: AT+CSVM=0  # this doesn't work
note: If the parameter <mode> is set to 0, the remaining parameters are ignored.

## Phonebook
- AT+CPBS          # Select phone book memory storage. **Must select a phonebook in order to store numbers**. 
  - AT+CPBS="SM"    # selected SIM card phone book; saves numbers to SIM card. 
- AT+CPBR          # read phone book entries
  - AT+CPBR=3      # returns phone number at phonebook entry=3.
  - AT+CPBR=1,4    # list entries 1 to 4. 
  - AT+BPBR=?      # returns list of supported indexes. 
- AT+CPBF          #
  - AT+CPBF="Jack" # Find Jack phone number.
  - AT+CPBF=?      # Find Jack phone number.
- AT+CPBW          # Write to phone book entry
  - AT+CPBW=1,"0220978888",129,"Jack"     # write to entry number 1 Jack's phone number.

# Audio Interface
- AT+CLVL=n     # set Loudspeaker volume level
  - AT+CLVL=3   # set volume level to 3. 
- AT+CLVL?      # returns the current volume level
- AT+CLVL=?     # return range of settable volume; e.g.: 1-5

## FTP
- UFTP
- UFTPC
- UFTPER

## HTTP
- UHTTP
- UHTTPAC
- UHTTPC
- UHTTPER

## MISC
- AT+CNUM - ??
- AT+WDDM - ??

## FOTA (for Sierra Wireless products)
- use airVantage (from Sierra wireless): https://www.sierrawireless.com/iot-connectivity/iot-cloud-platform/
- AT+WDSI=81,91
- AT+WDSS=1,1  # connec to airvantage?
- AT+WDSS=1,0  # close airVantage session?
- AT+KGSN=0  # get IMEI?
- AT+KGSN=3  # get ___ ??
- AT+CFUN=0  # ?? 





