# USAL-s-Studium-Watcher
Notifications via mail each time it changes, with the modified part and the pdfs attached

The cookies die after the browser closes, so we need to modify them not to perish and call wget with --keep-alive.
Execute the script on will or via crontab. 

·Fast example on how to configurate mail: (Debian/Ubuntu/etc. ) 


sudo apt-get install ssmtp

nano /etc/ssmtp/ssmtp.conf 
 	

        root=MailWhereYouWantTheMailsToBeSent@gmail.com    # <- 
        mailhub=smtp.gmail.com:587
        rewriteDomain=gmail.com
        hostname=WriteFullHostnameHere                      # <- 
        FromLineOverride=YES
        UseTLS=Yes
        UseSTARTTLS=YES
        AuthUser=HailHere@gmail.com                         # <- 
        AuthPass=PasswordHere                               # <- 


nano /etc/ssmtp/revaliases
        
        username:mailhere@gmail.com:smtp.gmail.com:587      # <- Put your mail here and your user name
        root:mailhere@gmail.com:smtp.gmail.com:587
