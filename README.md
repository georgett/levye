LEVYE - Brute force tool for penetration testers. 
=====

What is it?
---
**Levye** (crowbar) is brute forcing tool that can be used during penetration tests. It is developed to support protocols that are not currently supported by thc-hydra and other popular brute forcing tools. 
Currently **Levye** supports
 - OpenVPN 
 - SSH private key authentication
 + VNC key authentication 
 * Remote Desktop Protocol (RDP) with NLA support

Features
----
- Python based
- Multi-threaded
- Dont have dependencies to external programs like Nessus or Metasploit 
- Tested on Kali Linux 

Prerequisites
----
- Kali Linux
- Python 2.7+
- OpenVPN
- XfreeRDP
- VNCviewer

#### Installation

First you shoud install prerequisities 
apt-get install openvpn xfreerdp vncviewer ssh 

Then get latest version from github 
git clone https://github.com/galkan/levye 


#### Options

-h, --help  show this help message and exit  
-b {vnckey,openvpn,sshkey,rdp}, --brute {vnckey,openvpn,sshkey,rdp}
                     Brute Force Type  
  -s SERVER, --server SERVER
                        Server/Server File  
  -u USERNAME, --user USERNAME
                        Username/Username File  
  -n THREAD, --number THREAD
                        Thread Number.  
  -l LOG_FILE, --log LOG_FILE
                        Log File  
  -o OUTPUT, --output OUTPUT
                        Output File  
  -c PASSWD, --passwd PASSWD
                        Password/Password File  
  -t TIMEOUT, --timeout TIMEOUT
                        Timeout Value  
  -p PORT, --port PORT  Service Port Number.  
  -k KEY_FILE, --key KEY_FILE  Key File.  
  -m CONFIG, --config CONFIG Configuration File.  

#### Usage

./levye.py -b rdp -s 172.16.1.12/32 -u Administrator -c pass.txt  
./levye.py -b sshkey -s 127.0.0.1/32 -u root -p 22 -k id_rsa  
./levye.py -b vnckey -s 172.16.3.87/32 -p 5901 -c keys/vncpass  
./levye.py -b openvpn -s 172.16.1.100/32 -m server.ovpn -c pass.txt -u user.txt -k server.ca.crt -p 443  

#### Example output

cat levye.out 

#### TO DO 
- Finish readme file 
- Write example output file 
- upload example videos to youtube 
- preprare presentation for BH-Arsenal
