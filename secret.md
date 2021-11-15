# Sharepoint 2019 is exploitable  


## Some Terminologies  

* SSI ( Sever Side Inclusion ) is a simple interpreted server side scripting language used almost exculsively for the World Wide Web. It's most useful to include the contents of one or more files into a web page on the web server using the `#include` directive. This could be a common piece of code such as a page header, a page footer and a navigation menu.   
    <blockquote>
    It is supported by Apache, LiteSpeed, nginx, IIS as well as W3C's Jigsaw.
    </blockquote>   

* For the exploit to happen we need an account to log in and the permission to create pages (which is standard permission in Sharepoint).
* The exploits type seems to be called "Server-side Inclusion".   

* We can use the PUT HTTP method to upload some random data on a new page. The command is as follows:
    ```console
    kali> curl -X PUT -d "Testing PUT" --ntlm --negotiate -u Administrator:Default@123 --negotiate http://win-somelink/sites/test/sample.aspx
    ```  

* Then we access the new page view borwser to confirm we have file upload privilege.  

* Then, by using BurpSuite, we will create a file called ssi.aspx with a specific payload to  exploit the SSI vulnerability.  

* See the payload on this website 
<a href="https://medium.com/swlh/how-to-exploit-microsoft-sharepoint-for-ssi-and-viewstate-deserialization-a0a5cc3cd6ce">Exploit and the rest of the explanation</a>