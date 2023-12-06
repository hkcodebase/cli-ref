# Command Prompt

- [Commands](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/windows-commands)
- [Learning Reference](https://www.freecodecamp.org/news/command-line-commands-cli-tutorial/)
## Hardware 
- ```driverquery``` – Lists All Installed Drivers


## Directory
- ```cd``` or ```chdir```
- ```dir``` - list all directory
- ```del``` - del deletes a file
- ```attrib +h +s +r folder_name``` - hides a folder
- ```attrib -h -s -r folder_name``` - unhide folder
- ```tree``` - Shows the Tree of the Current Directory or Specified Drive
- 

## System
- ```systeminfo``` – Shows Your PC's Details
- ```set``` -  Shows your PC’s Environment Variables
- ```prompt``` - [change the command prompt](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/prompt)
- ``clip`` - [Redirects](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/clip) the command output from the command line to the Windows clipboard
- ```assoc``` – Lists Programs and the Extensions They are Associated With
- ```fc``` - Compares Two Similar Files
- ```sfc``` - System File Checker
- ```powercfg``` - Controls Configurable Power Settings
  - ```powercfg help```- show extensions
  - ```powercfg energy```- generate a battery health
- ```ver``` - shows version of OS
- ```tasklist``` - shows open programs
- ```taskkill``` - Terminates a Running Task
  - ```taskkill /IM <"task.exe"> /F```

## Command Prompt
- ```title```  – Changes the Command Prompt Window Title Using the Format
- ```color``` - change the color of command prompt
  - ```color attr``` - displays color options

## Networking
- [Netstat]((https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/netstat)) - "Netstat" is a tool for network statistics, diagnostics, and analysis
  - ```netstat -an``` – Shows Open Ports, their IP Addresses and States
- [Ping]((https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/ping))
  - ```ping``` - Verifies IP-level connectivity to another TCP/IP computer by sending Internet Control Message Protocol (ICMP) echo Request messages
- [IPconfig](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/ipconfig)
  - ```ipconfig``` Shows Information about PC IP Addresses and Connections
  - ```ipconfig /flushdns``` - switch to flush your DNS cache:
- [Nslookup](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/nslookup) - stands for Name Server Lookup.
  - ```nslookup www.google.com```
- [Getmac](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/getmac) - Every device that's compliant with IEEE 802 standards has a unique MAC address (Media Access Control). The manufacturer assigns MAC addresses and stores them in the device's hardware. Some people use MAC addresses to limit which devices can connect to the network.
  - ```getmac```
- [Pathping](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/pathping) -
  - ```pathping www.google.com```
- [Tracert](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/tracert) - "Tracert" stands for Trace Route. And much like "ping," it sends out a data packet as a way to troubleshoot any network issues you might have, but it instead tracks the route of the packet as it hops from server to server

## Can be useful

- [cipher](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/cipher)  - Wipes Free Space and Encrypts Data

## [Netsh]((https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/netsh))

"Netsh" stands for Network Shell. It's a cmd command for networking that lets you view and configure pretty much every network adapter on your system in more detail and granularity than any of the preceding commands.
Running the netsh command on its own will shift the Command Prompt into network shell mode. There are several different "contexts" within this shell, including one for routing-related commands, one for DHCP-related commands, and one for diagnostics, among others. But you can use it to run individual commands, too.

- ```netsh``` - Network Shell commnand
  - To see all network shell contexts
    ```
    netsh /?
    ````
  - To see all commands within a context
    ```
    netsh wlan /?
    ````    
  - Drill down one more layer to find all of the subcommands within those commands
     ```
    netsh wlan show /?
    ````   
  - List all Wi-Fi networks connected
    ```
    netsh wlan show profiles
    ````
  - List all drivers
    ```
    netsh wlan show drivers
    ````  
  - Below command shows All Wi-Fi Passwords
    ```
    for /f "skip=9 tokens=1,2 delims=:" %i in ('netsh wlan show profiles') do @echo %j | findstr -i -v echo | netsh wlan show profiles %j key=clear
    ```
