# Udacity-FSWD-Linux-Server-Config

# The IP address and SSH port so your server can be accessed by the reviewer:
Please give me your public key so that I can put it on the server. (Since it requires key based auth)  '
Then you should be able to:  
`ssh -i YOUR_PUBLIC_KEYFILE -p 2200 grader@54.197.209.114`  

# The complete URL to your hosted web application.
http://ec2-54-197-209-114.compute-1.amazonaws.com:8000/  

# A summary of software you installed and configuration changes made.
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

Open your ~/.ssh/udacity_key.rsa file in a text editor and copy the contents of that file.  
During the submission process, paste the contents of the udacity_key.rsa file into the "Notes to Reviewer" field.  
