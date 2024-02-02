86 % [ websites ] <== tested by whitehat sentinel had at least one serious vulnerability 
99.9 % [ exploited vulnerabilities ] <== were compromised more than the year after CVE was published
$ 500 M [ data breach ] [ Ashley Madison ]

User >> Presentation [ browser ] > Logic [ Web server ] > Firewall > Data [ database ]
        XSS,                                                            SQL Injection 
        Cross-site script forgery,                                      Lack of proper Access
        Exploiting Vulnerabilities 
         [ Transport Layer ]


Information Gathering  is a key step towards vulnerability discovery

        Scoping ==> Enumerating the targets [ target-list ]
                # Domain enumeration
                        % Theharvester <== fetch info regarding a domain
                                >> Theharvester -d <d omain_name> -b <google|linkedIn|bing>

                # Port scanning
                # Web apps defined by customer

        Fingerprinting ==> Gaining information related targets [ versions, infra, web servers, databases]
                # web-server & OS identification
                        % Head Request 
                        % HTTP header field ordering
                        % Malformed request
                        % nmap -p 80 - O
                        % httprint -h <ip> -s signatures.txt
                        % Netcraft
                        % whatweb

                # Content Management System [ CMS ] identification
                        % plugins make more vulnerable the CMS [ wordpress, joomla, drupal, PHPnuke, Mediawiki,...]  
                        % BlindElephant Tool [ Qualys ] 
                
                # Database Identification 
                        % Mysql - 3306 | MSSQL - 1433 | PostgreSQL - 5432 | Oracle - 1521 | DB2 - 50000
                        % SQL Injection
                        % string concatenation
                        % Error-based response 
                        % Unexpected single quote

        crawling ==> mapping web sites
                # Application Flow & Entry points identification
                        % Automated Crawling [ Application Mapping, listed referenced links, use authentication credentials]
                        % OWASP ZAP | Burp Suite 
                        % Entry Points [ HTTP methods, HTTP headers, Cookies, Uploads, URI ]

                # Successful sub-sections identification
                        % Educated Crawling [ Macros ]
                        % WebInspect  



                



                               
