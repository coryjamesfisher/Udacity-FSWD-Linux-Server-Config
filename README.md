# Udacity-FSWD-Linux-Server-Config

# The IP address and SSH port so your server can be accessed by the reviewer:
I have attached private key to the review notes. Password authentication is disabled so you will need to use it.  
I have also attached a temporary password so that you may use sudo commands. I have set it to expired, you will have to enter a new password.  
Here is the command to ssh to the server:  
`ssh -i udacity_review.rsa -p 2200 grader@54.197.209.114`

# Port Configurations
The ssh server is running on port 2200.  
The backend application is hosted on port 8080. The front end application is hosted on port 8000.  
I have blocked port 80 as it is not necessary for my application. This change also required tweaking
the apache configuration to serve from 8080 (/etc/apache2/ports.conf && /etc/apache2/sites-enabled/000-default).  
The nodejs server is a bit more homebrewed and runs with nohup but it listens on port 8000 from the /var/www/frontend/run script.  
Please see https://github.com/coryjamesfisher/Udacity-FSWD-Item-Catalog-Project for project details.  

# User Configurations
Users must log in using key based authentication. This change was forced in the /etc/ssh/sshd_config file.  
Both the ubuntu and the grader users have sudo rights. I have tightened both down with files in /etc/sudoers.d so that they require the user to enter their password (amazon defaulted the ubuntu user to passwordless sudo).

# The complete URL to your hosted web application.
http://ec2-54-197-209-114.compute-1.amazonaws.com:8000/  

# A summary of software you installed
*Note all software was installed after running sudo apt-get update && sudo apt-get upgrade*  
I have installed all of the following:  
postgres, apache, apache mod wsgi, git, nodejs, npm (and npm modules), python(and related modules)  

# A list of any third-party resources you made use of to complete this project.
https://discussions.udacity.com/t/markedly-underwhelming-and-potentially-wrong-resource-list-for-p5/8587 (tons of help)  
https://discussions.udacity.com/t/allowing-additional-ports-problem/183585/3 (my own thread)  
http://askubuntu.com/questions/17823/how-to-list-all-installed-packages (just to double check what I thought and saw in bash history)  
http://stackoverflow.com/questions/26428488/reactify-browserify-and-gulp-typeerror-object-transform-has-no-method-tra (Had to minify the js file since it was almost 3 mb and was sooo slow!)  
http://babeljs.io/docs/plugins/preset-stage-1/ (help with minify)  
https://github.com/babel/babelify (help with minify)  
https://ubuntuforums.org/showthread.php?t=1893751 (UFW)  
https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps (wsgi)  
http://unix.stackexchange.com/questions/112023/how-can-i-replace-a-string-in-a-files (sed script to fix urls from localhost to amazon url in my project)  
http://stackoverflow.com/questions/17161345/how-to-open-a-web-server-port-on-ec2-instance (trying desperately to open ports in udacity's instances only to find out that they can't be opened :) )  
http://httpd.apache.org/docs/current/bind.html (while double checking my knowledge of ports in apache (I'm a php developer so I use apache semi-regularly))  
https://www.google.com/webhp?sourceid=chrome-instant&ion=1&espv=2&ie=UTF-8#q=enable%20proxypass%20apache2 (when I tried to work around the single http port problem with proxies but failed because the application changes were too big)  
https://www.postgresql.org/docs/9.1/static/app-createuser.html (Looked this up only to remember I had it saved in my provision.sh for vagrant)  
http://askubuntu.com/questions/323131/setting-timezone-from-terminal (Figured out how to set timezone to UTC)  

I am probably missing a few I did a lot of research in getting this server set up.  
