# Machine #9 Jarvis  


## Nmap Results  
  <img src="https://nmap.org/images/nmap-logo-256x256.png">   

* Initial nmap output  

  ```console
  PORT   STATE SERVICE
  22/tcp open  ssh
  80/tcp open  http
  ```  

* Full scan gave the same results.

<br/><br/>

## Banner Grabbing of Services  

* The ssh
  ```console
  PORT   STATE SERVICE VERSION
  80/tcp open  http    Apache httpd 2.4.25 ((Debian))
  ``` 

* The http  
  ```console
  PORT   STATE SERVICE VERSION
  22/tcp open  ssh     OpenSSH 7.4p1 Debian 10+deb9u6 (protocol 2.0)
  Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel
  ```  

<br/><br/>

## Searchsploiting Results   
  <img src="https://www.offensive-security.com/wp-content/uploads/2020/05/SearchSploit-1.png" width=400 height=200>   

* Nothing significant search just yet. 

<br/><br/>  

## Gobustering Stuff  
  <img src="https://cdn.akamai.steamstatic.com/steam/apps/1092880/capsule_616x353.jpg?t=1605640630" width=400 height=200>  


* Gobustering root `/`  
  ```console
  /connection.php       (Status: 200) [Size: 0]  
  /css                  (Status: 301) [Size: 310] [--> http://10.10.10.143/css/]
  /fonts                (Status: 301) [Size: 312] [--> http://10.10.10.143/fonts/]
  /footer.php           (Status: 200) [Size: 2237]                                
  /images               (Status: 301) [Size: 313] [--> http://10.10.10.143/images/]
  /index.php            (Status: 200) [Size: 23628]                                
  /js                   (Status: 301) [Size: 309] [--> http://10.10.10.143/js/]    
  /nav.php              (Status: 200) [Size: 1333]                                 
  /phpmyadmin           (Status: 301) [Size: 317] [--> http://10.10.10.143/phpmyadmin/]
  /room.php             (Status: 302) [Size: 3024] [--> index.php]                     
  /server-status 
  ```  

* Gobustering `/phpmyadmin`  
  ```console
  /ChangeLog            (Status: 200) [Size: 19186]
  /LICENSE              (Status: 200) [Size: 18092]
  /README               (Status: 200) [Size: 1520] 
  /ajax.php             (Status: 200) [Size: 15219]
  /changelog.php        (Status: 200) [Size: 15215]
  /doc                  (Status: 301) [Size: 321] [--> http://10.10.10.143/phpmyadmin/doc/]
  /examples             (Status: 301) [Size: 326] [--> http://10.10.10.143/phpmyadmin/examples/]
  /export.php           (Status: 200) [Size: 15213]                                             
  /favicon.ico          (Status: 200) [Size: 22486]                                             
  /import.php           (Status: 200) [Size: 15223]                                             
  /index.php            (Status: 200) [Size: 15211]                                             
  /js                   (Status: 301) [Size: 320] [--> http://10.10.10.143/phpmyadmin/js/]      
  /libraries            (Status: 301) [Size: 327] [--> http://10.10.10.143/phpmyadmin/libraries/]
  /license.php          (Status: 200) [Size: 15210]                                              
  /locale               (Status: 301) [Size: 324] [--> http://10.10.10.143/phpmyadmin/locale/]   
  /logout.php           (Status: 200) [Size: 15213]                                              
  /navigation.php       (Status: 200) [Size: 15221]                                              
  /phpinfo.php          (Status: 200) [Size: 15252]                                              
  /robots.txt           (Status: 200) [Size: 26]                                                 
  /robots.txt           (Status: 200) [Size: 26]                                                 
  /setup                (Status: 301) [Size: 323] [--> http://10.10.10.143/phpmyadmin/setup/]    
  /sql                  (Status: 301) [Size: 321] [--> http://10.10.10.143/phpmyadmin/sql/]      
  /sql.php              (Status: 200) [Size: 15207]                                              
  /templates            (Status: 301) [Size: 327] [--> http://10.10.10.143/phpmyadmin/templates/]
  /themes               (Status: 301) [Size: 324] [--> http://10.10.10.143/phpmyadmin/themes/]   
  /themes.php           (Status: 200) [Size: 15236]                                              
  /tmp                  (Status: 301) [Size: 321] [--> http://10.10.10.143/phpmyadmin/tmp/]      
  /url.php              (Status: 302) [Size: 0] [--> /phpmyadmin/]                               
  /vendor               (Status: 301) [Size: 324] [--> http://10.10.10.143/phpmyadmin/vendor/] 
  ```

<br/><br/>

## Thinking Out Loud   

  <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQr4hzX6KoRN5PjPJjy8QC43K0T-CoXZHawDIxG4jCa9aMD1K8Vl3vhpG2a2OVbiy-i93c&usqp=CAU" width=200 height=200>  

  * So depending on the tags of the machine seems like I have to do an sqli in one way or another. I will try sqlmap. `sqlmap -u 10.10.10.143/myphpadmin --data='set_session=5qrjovmconhvga09mp1jjs55no0l6mq3&pma_username=admin&pma_password=admin&server=1&target=index.php&token=OVAQ%5BCV7zODc%3EEgg' --method POST --dbs --batch`.

  * It does not make any sense to use it anyway because the only parameter I have is the `cod=` which seems to be the parameter for the room's code.


  gobuster dir -u http://10.10.10.143 -x php,txt,html -w /home/kali/SecLists/Discovery/Web-Content/big.txt

  * Found a directory called `/connection.php` when doing `gobuster`.
  * The results  


  * Found a page called `/myphpadmin` and it is a login page which means that I might be able to do the sql injection from there or anything else.

  * Found this `http://10.10.10.143/phpmyadmin/setup/index.php`. Seems like it's not supposed to be accessabile to the public even tho it it.


  * Gobustering `/phpmyadmin` is a gem I've got tons of directories that seem to be useful (Most of them at least)  


  * Seems like phpmyadmin uses a templating engine called 'Twig' and this might allow me to do a Server-Side Template Injection that might be equivalent to sql injection. One of the tags was just "Injection" which could mean that it might be another type of injection. 
  * I can get an RCE through this injection vulnerability.

<br/><br/>

## How Did I Solve the Challenge   

   <img src="https://images.lifesizecustomcutouts.com/image/cache/catalog/febProds21/SP000081-500x500.png" width=200 height=200> 