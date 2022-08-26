This script is used to prober an SNMP agent and find the rate of change for several OIDs between successive probes/samples. 
The two simulators used to test this is reacheable via 18.219.51.6 port 1611 and port 1612. The one on port 1611, is behaving a bit better than the one in 1612. Their community strings are 'public'.

The script will be invoked as follows:  

# prober <Agent IP:port:community> <sample frequency> <samples> <OID1> <OID2> ……... <OIDn>   

IP, port, and community are agent details, OIDn are the OIDs to be probed (they are absolute, cf. IF-MIB::ifInOctets.2 for interface 2, or 1.3.6.1.2.1.2.2.1.10.2 [1])   
Sample frequency (Fs) is the sampling frequency expressed in Hz, you should handle between 10 and 0.1 Hz.  
Samples (N) is the number of successful samples the solution should do before terminating; hence the value should be greater or equal to 2. If the value is -1 that means run forever (until CTRL-C is pressed, or the app is terminated in some way).  
