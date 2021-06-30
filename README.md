# WebUIForKubernetes
This projects lets you run kubernetes command from the web browser even if you do not know the exact command.

To use Your minikube VM as a client you need to copy the 'admin.conf' from sudo cd /etc/kubernetes/ [ minikube VM ] to sudo cd /root/.kube/
after renaming the file as 'config'.

You also need to change the server address in admin.conf file before renaming the file :

-----------------------------------------------------------------------------------------------------------------------------------
| IN 'admin.conf' :        change                                                                                                       |
|            server: https://control-plane.minikube.internal:8443                                                                 |
|                                  to                                                                                             |
|            server: https://xxx.xxx.xxx.xxx:8443            [ xxx.xxx.xxx.xxx is the IP address of your minikube VM ]            |
|                                                                                                                                 |
-----------------------------------------------------------------------------------------------------------------------------------
