# LAN - Automated Network Reconnaissance
Simple Python Script for automatically discovering what devices are connected to a Local Network (Operating Systems & Open Ports included)

# Resources
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

> Navigate to the directory where the script is located and use "python 'name_of_.py' to run script against your locally connected network"

> A seperated list of each device on the network along with it's operating system is then produced

--------------------------------------------------
      IP: 10.x.x.x
      OS Name: Apple Mac OS X 10.11 (El Capitan) or iOS 12.4 - 13.6 (Darwin 15.6.0 - 19.6.0)
      OS Accuracy: 97

      OS Name: Apple macOS 10.15 (Catalina) (Darwin 19.6.0)
      OS Accuracy: 97

      OS Name: Apple macOS 10.13 (High Sierra) - 10.15 (Catalina) or iOS 11.0 - 13.4 (Darwin 17.0.0 - 19.6.0)
      OS Accuracy: 96

    OS Name: Apple macOS 11 (Big Sur) (Darwin 20.6.0)
    OS Accuracy: 96

    Port scan results:
    Protocol: tcp
    Port: 49153 Service:
    Port: 62078 Service: iphone-sync
--------------------------------------------------
    IP: 10.x.x.x
    OS Name: Amazon Kindle Paperwhite
    OS Accuracy: 100

    OS Name: CyanogenMod 12 (Android 5.0.2)
    OS Accuracy: 100

    Port scan results:
    Protocol: tcp
    Port: 8009  Service: ajp13
    Port: 9080  Service: glrpc
--------------------------------------------------
    IP: 10.x.x.x
      OS Name: VxWorks
      OS Accuracy: 99

    OS Name: Keyence CV-X150F Image Sensor/Controller (VxWorks)
    OS Accuracy: 97

    OS Name: VxWorks: HP printer or Vocality BASICS Four Wire VoIP gateway
    OS Accuracy: 97

    OS Name: HP LaserJet M2727nf or P1505n printer
    OS Accuracy: 96

    OS Name: Blackboard transaction system serial-to-IP converter
    OS Accuracy: 96

    OS Name: HP LaserJet CP2025dn printer
    OS Accuracy: 96

    OS Name: HP LaserJet M451dn, CM1415fnw, or CP4525
    OS Accuracy: 96

    Port scan results:
      Protocol: tcp
    Port: 80    Service: http
      Website: http://10.x.x.x:80
    Port: 139   Service: netbios-ssn
    Port: 443   Service: https
      Website: http://10.x.x.x:443
    Port: 445   Service: microsoft-ds
    Port: 631   Service: ipp
    Port: 8080  Service: http-proxy
    Port: 9100  Service: jetdirect
    Port: 9220  Service:
--------------------------------------------------
    IP: 10.x.x.x
    OS Name: Apple macOS 11 (Big Sur) (Darwin 20.6.0)
    OS Accuracy: 100

    Port scan results:
    Protocol: tcp
    Port: 49152 Service:
    Port: 62078 Service: iphone-sync
--------------------------------------------------
    IP: 10.x.x.x
    OS Name: Microsoft Windows 10 1607
    OS Accuracy: 100

    Port scan results:
      Protocol: tcp
        Port: 135   Service: msrpc
        Port: 139   Service: netbios-ssn
        Port: 445   Service: microsoft-ds
        Port: 2869  Service: icslap
        Port: 5357  Service: wsdapi
--------------------------------------------------
    IP: 10.x.x.x
      OS Name: Amazon Kindle Paperwhite
      OS Accuracy: 100
    
      OS Name: CyanogenMod 12 (Android 5.0.2)
      OS Accuracy: 100
    
    Port scan results:
      Protocol: tcp
        Port: 8009  Service: ajp13


