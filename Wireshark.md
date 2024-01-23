
Wireshark      ==> open-source app. that captures & displays data travelling back & forth on a netrwork
                = Ethereal [ original name ]   || network packet analyzer
                = displays data from different protocols on all major network types
                = supports dozens of capture/trace file formats [ CAP, ERF ]




        ? Profile <== Set of configurations or settings 
        ? Wireshark dissector
        ? Delta Time
        ? libpcap | Npcap | UsbPcap 
        ? gns3




                @ Windows -
                          - Download [ https://www.wireshark.org/download.html ]
                          - Install it [ Npcap | USBPcap]
                          - run it as administrator

                @ Linux   - 
                           >> sudo apt update
                           >> sudo apt upgrade
                           >> sudo add-apt-repository ppa:wireshark-dev/stable  [ optional ]
                           >> sudo apt install wireshark
                           >> sudo dpkg-reconfigure wireshark-common
                           >> sudo usermod -aG wireshark $(whoami) || sudo usermod -aG wireshark $USER
                           >> sudo chmod 4711 `sudo which dumpcap` [ use this when dump issues ]
                           >> sudo wireshark  



            >> dumpcap -h
            >> dumpcap -D
            >> dumpcap -i ${interface_id}
            >> dumpcap -i ${interface_id} -w ${path-of-the-file-to-save-pcapng}
            >> dumpcap -i ${interface_id} -w ${path-of-the-file-to-save-pcapng} -b filesize:100000 -b files:10