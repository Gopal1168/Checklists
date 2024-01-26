Windows  ==> GUI 
            = Command Line Interface-driven predecessor [ PC-DOS ] [ 1981 ] [ 86-DOS ]
            = DOS <== Disk Operating System [ entire CLI driven ]
            = Windows 3.1 [ 1991 ] [ click, drag, manipulate forms and graphical objects on screen ]
            = Windows 95 [ 1995 ]

            = Powershell < Commandline-shell + Scripting Language >
            = case - insensitive


    https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/windows-commands     <== Windows Commands Link>
    


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
    
    ? Creating a new file in windows 
        >> type nul > file1.txt
        >> fsutil file createnew file2.txt 0
        >> copy con file3.txt

    ? Find a particular word or string in a directory - findstr "STRING" ${Path-of-directory}*.txt


File Systems ==> The way of organizing files, folders, storage and peripherals [ Hierarchial Order ]
                 Volumes > Folders > Files

                = FAT16, FAT32, exFAT[ Extended File Allocation Table ] => USB 
                  NTFS [ New Technology File System ] [ 1993 ][ 16TB to 8PB ]

            Local Disk [ C drive ] -
                % EFI [ Exgternsible Firmware Interface ] = boot files & partitions 
                  BCD [ Boot Configuration Data ]         = holds info about the boot options 
                  
                % PerfLogs = Performance monitors saves its data | find bottlenecks & troubleshoot issues
                           = Deleted > Windows Recreated it

                % Program File [ x86 ] = installed programs files 
                                       = x86 ==> 32-bit programs & another one ==> 64-bit programs

                % Program Data = applications can store data that is not user-specific


#### use QUOTES while referencing long names with spaces in CMD | POWERSHELL

        start-up folder [ shell:startup [win + R] ] <== used to automatically run scripts & programs at start-up
        .bat ==> batch file ,contains a sequence of commands stored in plain text
        SAM [Security Account Manager] <== stores sensitive info such as user accounts, passwords, security descriptors
                    C:\Windows\System32\config
                        = highly secure db file 
                        = chntpw <== used to alter the SAM database

        Registry Editor [ regedit [Win + R] ] <== Hierarchial db, used to store data for programs & hardware installed on OS
                    = registry hive is a logical grouping of key-value pairs

        %SystemRoot% = C:\Windows
        echo %PATH%  = results all the Path environmental variables & corresponding values
        sysdm        = open System Properties windows

        ADS [ Alternate Data Streams ] = used to hide data inside other data

            >> echo content > host filename.extension:ads

        
            Default Apps > Choose default apps by file type 








