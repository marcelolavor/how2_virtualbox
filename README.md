# how2_virtualbox
Virtual box adjustments


## How to turn off windows hypervisor (when VirtualBox VMs running slow)
Ref: https://forums.virtualbox.org/viewtopic.php?f=6&t=92260

1. Open CMD windows as Administrator
2. Execute the followinf commands
```
dism.exe /Online /Disable-Feature:Microsoft-Hyper-V
bcdedit /set hypervisorlaunchtype off
```

## How to create Port Forwarding

1. In Oracle VirtualBox, go to the "Host Network Manager" and identify the adaptor IP address for "VirtualBox Host-Only Ethernet Adaptor"

Ex: 192.168.56.01

2. Open and edit the "hosts" file

C:\Windows\System32\drivers\etc\hosts (Windows)
or 
/etc/hosts (Linux)

3. Add the following line

192.168.56.01	box

4. In order to add the NAT rule in the VM, at "Devices" menu, access the sequence Network\Network Settings\Adapter 1\Advanced\Port Forwarding\Add\

5. Add the folllowing registry for "Port Forwarding" as per mentioned below:

NAME: 		Example
PROTOCOL:	TCP
HOST IP:	192.168.56.01
HOST PORT:	5601
GUEST IP:	10.0.2.15
GUEST PORT:	5601

