# USAL-s-Studium-Watcher
Notifications via mail each time it changes, with the modified part and the pdfs attached

The cookies die after the browser closes, so we need to modify them not to perish and call wget with --keep-alive.
Execute the script on will or via crontab. 

·Fast example on how to configurate mail: (Debian/Ubuntu/etc. ) 

sudo apt-get install ssmtp
nano /etc/ssmtp/ssmtp.conf 

#
# Config file for sSMTP sendmail
#
# The person who gets all mail for userids < 1000
# Make this empty to disable rewriting.
root=MailWhereYouWantTheMailsToBeSent@gmail.com    # <- 

# The place where the mail goes. The actual machine name is required no
# MX records are consulted. Commonly mailhosts are named mail.domain.com
mailhub=smtp.gmail.com:587

# Where will the mail seem to come from?
rewriteDomain=gmail.com

# The full hostname
hostname=WriteFullHostnameHere                      # <- 

# Are users allowed to set their own From: address?
# YES - Allow the user to specify their own From: address
# NO - Use the system generated From: address
FromLineOverride=YES

# Use SSL/TLS before starting negotiation
UseTLS=Yes
UseSTARTTLS=YES

# Username/Password
AuthUser=HailHere@gmail.com                         # <- 
AuthPass=PasswordHere                               # <- 



nano /etc/ssmtp/revaliases

username:mailhere@gmail.com:smtp.gmail.com:587      # <- Put your mail here and your user name
root:mailhere@gmail.com:smtp.gmail.com:587
