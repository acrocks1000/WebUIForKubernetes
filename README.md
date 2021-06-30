# WebUIForKubernetes
This projects lets you run kubernetes command from the web browser even if you do not know the exact command.

-> Place the home3.html and the Color.gif files in /var/www/html/ directory and all the python files in /var/www/cgi-bin/ directory. [In RHEL8]

    Note: You may need to recreate all the python files and then convert then to executable using [chmod +x file_name] as these python are already converted to executable
    file in my system and some settings may vary from system to system. [Otherwise may or may not giving an Internal Server Error]

-> This project uses minikube VM for kubernetes services and RedHat 8 OS as the apache webserver host OS. [ In my case running on top of Virtual Box ].
You need to have the following setting in RedHat OS to configure the Web UI successfully

1. Have an apache server installed (yum install httpd)
2. disabe firewall [ Technically this step should be allowing various permisssions however as this project is not security based so i used an unsecure round about way] (systemctl disable firewalld)
3.give apache root access through suoders (sudo gedit /etc/sudoers    :
  IN /etc/sudoers :
              ## Allow root to run any commands anywhere 
              
               root	ALL=(ALL) 	ALL

               apache  ALL=(ALL)       NOPASSWD: ALL
               
4. setenforce 0       [set SElinux mode from targeted to passive]



-> To use Your minikube VM as a client you need to copy the 'admin.conf' from sudo cd /etc/kubernetes/ [ minikube VM ] to sudo cd /root/.kube/ [RedHat 8 OS]
after renaming the file as 'config'.

You also need to change the server address in admin.conf file before renaming the file :

-----------------------------------------------------------------------------------------------------------------------------------

 IN 'admin.conf' :        change               
 
            server: https://control-plane.minikube.internal:8443   
            
                                  to          
                                  
            server: https://xxx.xxx.xxx.xxx:8443            [ xxx.xxx.xxx.xxx is the IP address of your minikube VM ]            
                                                                                                                                 
-----------------------------------------------------------------------------------------------------------------------------------
