# Automated-Network-Reconnaissance
Simple Python Script for automatically discovering what devices (&amp; operating systems) are connected to a network 

# Resources Used 
PyCharm | https://www.jetbrains.com/pycharm/download/?section=windows

Python | https://www.python.org/downloads/

Terminal | https://learn.microsoft.com/en-us/windows/terminal/

<h2>Python Raw Script</h2>
  
     # Print port scan results
                 import nmap
    # Initialize the PortScanner object
               nm = nmap.PortScanner()
    # Define the target IP range 
               target_ip = "x.x.x.x/x
     # configure Nmap options for OS detection with --osscan-limit and --osscan-guess
               nmap_options = "-O --osscan-limit --osscan-guess"
                 nm.scan(hosts=target_ip, arguments=nmap_options)
    # format the results
          for host in nm.all_hosts():
          if 'osmatch' in nm[host]:
          print(f"IP:{host}")
          for 'osmatch in nm[host]['osmatch']:
              print(f' OS name: {osmatch['name']}")
                print(f" OS Accuracy: {osmatch['accuracy']}")
                print()
             print("Port scan results:")
               for proto in nm[host].all_protocols():
                 print(f"  Protocol: {proto}")
                 ports = nm[host][proto].keys()
                   for port in ports:
               service = nm[host][proto][port]['name']
               print(f"    Port: {port}\tService: {service}")

      # Check if it's HTTP or HTTPS port
               if port in [80, 443] and service in ['http', 'https']:
                   print(f"      Website: http://{host}:{port}")

     # Add separator after each IP address
             print("-" * 50)

           else:
             print(f"IP: {host} - OS detection not available")

# Example Output
