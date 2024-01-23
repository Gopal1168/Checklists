Nmap ==> Network Mapper 
       = used to reconnaissance or footprinting the target networks
       = Nmap is a powerful network scanning tool used to discover hosts and services on a network
    
       terminal > sudo root > nmap --help


       https://nmap.org/                             == Nmap official website
       http://scanme.nmap.org/                       == Sample website to apply scanning using nmap
       https://www.nirsoft.net/countryip/            == Major IP Addresses based on Country
       https://ipinfo.io/ips                         == All ip address along with their registered company info.
       https://tools.tracemyip.org/lookup/${ip-addr} == To get info regarding a particular ip address


        = easily detect-able by firewalls 


                -V <== Verbose | prints version number
                -A <== Enable OS detection, version detection, script scanning, traceroute [ Aggressive Scan ]
                -oG <== Grippable output
                -vv <== double verbose, provides more info.
                -p  <== used to scan particular ports
                -sV <== services versions
                -F <== Fast & most common tagetted ports [ 100 ports ]
                --open <== scan open ports only
                -oX  <== Save the output in xml format


                      >>  nmap scanme.nmap.org  <== scanning for open ports | Time-taking process
                                                = scan 1000 ports [ def ], 6500 ports [ limit ]

                      >>  nmap -oG ${inet}[ 3 octets ].0 255 -vv > ${path-to-file-to-save}
                      >>  nmap -oG ${inet}[ 3 octets ].0 255 -p 22 -vv > ${path-to-file-to-save}
                      >>  nmap -A scanme.nmap.org
                      >>  nmap -sV scanme.nmap.org 
                      >>  nmap -F scanme.nmap.org 
                      >>  nmap -F scanme.nmap.org www.google.com ${ip-addr}
                      >>  nmap --open scanme.nmap.org
                     




ZENMAP ==> Provide GUI for nmap
            Open as SuperUser > Target > Profile > Scan

WebMap ==> Github repo | alternative for ZenMap [ https://github.com/SabyasachiRana/WebMap ]

                >> curl -sL http://bit.ly/webmapsetup | bash
                >>  nmap -sV -sC ${ip-addr} -oX ${path-to-xml-file-to-save-in-webapp-in-tmp}


NSLOOKUP ==> Name Server Look Up 
           = used to fetch ip address or server name 

           nslookup ${server_name}
           nslookup ${ip-addr} 