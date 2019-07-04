# What-I-learn-from-Jenkins
Problems and solutions with Jenkins

**Install jenkins**

- Download pkg from the Jenkins website. https://jenkins.io 
  If you download package and install, jenkins will create a new user for you and the process will run under user "jenkins".           This may cause accessibility issues because your script may need other user to run.

To solve this potential problem, I recommend brew install.
- Use Brew to install jenkins: **brew install jenkins** \
  Run java -jar /usr/local/Cellar/jenkins/**VERSIONNUMBER**/libexec/jenkins.war --httpPort=8080
  create org.jenkins-ci.plist file in ~/Library/LaunchDaemons
  
File content can be found in this repo
  
  
Run ***sudo chown root /usr/local/Cellar/jenkins/2.122/homebrew.mxcl.jenkins.plist***
  
Launch Jenkins by ***localhost:8080*** and you need to key in the initial admin password (you can find it in the terminal instead of go to the file)
  
 St up all the accounts etc.
  
 Then you can start a free style app.
  
 Things you need to do:
  
 - Set up remote git url with necessary credential. 
   git remote -v to get url and ~/.SSH to get you private key.
 - Set build trigger. If you wanna build periodically, here are some examples: H/5 * * * * (build every 5 min), H H/2 * * * (build every 2 hours), H 12 * * * (build at 12 pm)
 - Then you can add your build action. 
    For ios project i am using script to build and archive instead of set up xcode build.
    If you want to use xcode build you need to install necessary plugins. (for example: xcode integration)

 - If you are launching a local script, you need to put the script at correct location.
 The pulled code is at /Users/iosdev/.jenkins/workspace/***RPROJECTNAME***/
 
Now you can try to build 



***PROBLEMS***

- YOU NEED TO UPDATE PODS SO REMEMBER TO DO POD UPDATE IN THE SCRIPT!
- HOW TO CHANGE IP ADDRESS FROM LOCALHOST? \
  well,what i did is first go to global config and change the URL
  then ***brew services stop jenkins***
  then i start jenkins with ***jenkins*** instead of brew services start jenkins
 
    
  
  




