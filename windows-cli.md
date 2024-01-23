Windows  ==> GUI 
            = Command Line Interface-driven predecessor [ PC-DOS ] [ 1981 ] [ 86-DOS ]
            = DOS <== Disk Operating System [ entire CLI driven ]
            = Windows 3.1 [ 1991 ] [ click, drag, manipulate forms and graphical objects on screen ]
            = Windows 95 [ 1995 ]

            = Powershell < Commandline-shell + Scripting Language >
            = case - insensitive


    https://learn.microsoft.com/en-us/windows-server/administration/windows-commands     <== Windows Commands Link>


    cmd             whoami              dir                 tree                help                mkdir
    echo            > | >>              type                copy                findstr             rename
    del             rmdir               doskey /history     systeminfo          tasklist            date 
    time            sc                  more                net                 ipconfig            ping
    nslookup        nestat              net user            findstr



        net user  = list all local user accounts
        net help user  = display the help guide 
        net localgroup = list all groups on the lab server
        net accounts   = view the current password requirements


    for /L %a in (1,1,255) do @ping -n 1 -w 10 10.91.x.%a > null && echo 10.91.x.%a is up!


    ? FINDING NO.OF USER ACCOUNTS ON WINDOWS SERVER ==> compmgmt.msc [ Computer Management ] > Local Users & Groups > Users
    ? FINDING NETWORK SHARES EXIST ON WINDOWS SERVER ==>  net share || get-smbshare || compmgmt.msc [ Computer Management ] > Shared Folder > Shares
    


