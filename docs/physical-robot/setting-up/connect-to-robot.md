---
layout: default
title: Connect to Robot
parent: Setting Up
grand_parent: Physical Robot
nav_order: 2
has_toc: false
---

# Connect to SMB Physical Robot
{:.no_toc}

In the following, the basic usage of the SMB payload is described.

* Table of contents
{:toc}

## Powering up the payload
The SMB payload can be powered by either the SMB payload power supply or a payload battery. You can also plug several power sources (e.g. power supply and battery). While the payload power supply is plugged, the battery will not be discharged but also not charged. Once the power supply is disconnected, the system automatically switches over to the first battery (as long as it it charged enough) and subsequently to the second battery.

### Connecting the Battery
Please be sure that you are well informed about the type of the battery you are using. Read the safety document and do not hesitate to ask for help if you are not sure about something!
{: .warning }

While placing the battery into its drawer, visually verify that the wires are not twisted, sheared or wedged into something!
{: .warning }

If you notice or suspect even a small amount of expansion on the battery, inform your supervisor!
{: .warning }

Do not cut the wires!
{: .warning }

Be sure that wire tips are connected to the right way as the color of connected tips should be same! 
{: .warning }

Li-Ion batteries are affected by the same problems as other lithium based batteries. This means that overcharge, over-discharge, over-temperature, short circuit, crush and nail penetration may all result in a catastrophic failure, including the pouch rupturing, the electrolyte leaking, and fire.
{: .warning }

### Turning on the SMB payload
In order to power-up the computer on the SMB use the [Payload Power Switch](../images/SMB_Backpanel.png). Close the lid of the switch to prevent shut-down by mistake.

## Connecting to the SMB 

### Remark
In the document there are two terminal types:

1. Terminal of host PC: The terminal that has access to host pc system.
   
2. Terminal of SSH: The terminal that has SSH connection to the SMB, therefore has access to the SMB system.

### Connect to the SMB network
In order to connect to SMB, you can either use the Wifi of the SMB or connect using a ethernet cable.

Use the following details of the wireless network of the SMB: 
  * Wifi (SSID): SMB_26x
  * Password: SMB_26x_RSS
  
*where x is the last digit of SMB Robot Number*


Once you are connected, from the terminal you should connect the SMB via SSH. 

**The ip addresses of every SMB is 10.0.x.5 where x is the last digit of SMB Robot Number**.
*Example: For SMB 263 the on-board computer IP address is 10.0.3.5*
{: .note }

Note that there might be an error in the host PC while trying to connect the SMB via ssh. Please read the terminal and use the suggested command in terminal to remove the previous ssh connection settings. 
{: .note }

```bash
# In the terminal of host pc
# Do not forget to change x and <user>
ssh <user>@10.0.x.5
# Password: <password>
```

**You should connect to the SMB with your given username. The Username is your team number**.
*Example: For team 1, the username is team1*
{: .note }


Once you are connected to the SMB you will see an IP address and port tuple on the terminal starting with `http://`. Please save it since we will need it in the next step. 

```

#### Network Sharing

Whenever the 4G connection is not working well, you can connect the SMB NUC to another Wi-Fi using,

```bash
#! Terminal becomes terminal of SSH! 

# To view connections available, this shows the list of connections available to join
nmcli connection show

# To connect the SMB to Internet (you can specify the connections available from above command, e.g: sudo nmcli connection up mavt-asl-iot)
sudo nmcli connection up
```


## How to establish the VPN connection on robot? (Optional)

This documentation explains the basic steps about how to connect your host machine to the SMB via VPN connection. We use KasmVNC to connect to the robots via 4G.
The following instructions will contain the configurations for SMB264.

### Installation

```bash
vncserver :2
```
2. Go to 
```bash 
http://10.0.x.5 
```
3. The default username and password are `robotx`.
4. Click Ok.
5. To kill the vncserver 
```bash
`vncserver -kill :2`
```
**The ip addresses of every SMB is 10.0.x.5 where x is the last digit of SMB Robot Number**.




#### Connect to the SMB
To enter the SMB just `ssh` into it as described in the Connecting to the SMB section. Please, make sure that you are not connected to the local SMB network.

