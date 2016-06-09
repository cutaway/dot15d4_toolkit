# Dot15d4 Toolkit
IEEE 802.15.4 (Zigbee/Zwave/900MHz) Testing Tools Installed on Ubuntu

## Docker Image
The Dockerfile contains the instructions to build a Docker image containing tools to test IEEE 802.15.4 testing tools. These tools include:

* [KillerBee](https://github.com/riverloopsec/killerbee) - the version currently maintained by [River Loop Securitys](http://www.riverloopsecurity.com/index.html)
* [Scapy-com](https://bitbucket.org/cutsec/scapy-com) - a fork of the original [SecDev Scapy-com](https://bitbucket.org/secdev/scapy-com)
* [rfcat](https://bitbucket.org/atlas0fd00m/rfcat) - a 900 MHz analysis framework by [atlas](https://twitter.com/at1as?lang=en) 
* [KillerZee](https://github.com/joswr1ght/killerzee) - Z-Wave analysis tools by [Josh Wrights](https://twitter.com/joswr1ght?lang=en) 
* [InGuardians' ZigBee Tools](https://github.com/inguardians/zigbee_tools) - A few ZigBee Tools to compliment KillerBee. 
** zbdump_display2 - an update of zbdump that displays packets to STDOUT so that you know the tool is capturing packets.
** zbanalyzer - a tool to leverage Cutaway's update Scapy-com ZigBee layer to leverage Scapy-style output of ZigBee communications.

## Helpful Notes
### Docker Shells
To get a shell on a Docker container you can use the built in mechanisms provide through Kitematic. However, on Windows, this opens a shell in the PowerShell terminal. While robust, the PowerShell terminal does not handle output from the Docker terminals well. Therefore I recommend using a different terminal, such as Cygwin, to access the container.

1. SSH to Docker IP Address: ```ssh docker@192.168.99.100```
2. Open terminal to Docker Container: ```docker exec -i -t <image_id> /bin/bash```
3. Leverage screen to provide logs and better shell interactions: ```docker exec -i -t <image_id> bash -c "exec >/dev/tty 2>/dev/tty </dev/tty && /usr/bin/screen -s /bin/bash"```

## References
* Using Screen in docker: https://github.com/docker/docker/issues/728
* Connect to a container: http://stackoverflow.com/questions/17903705/is-it-possible-to-start-a-shell-session-in-a-running-container-without-ssh

