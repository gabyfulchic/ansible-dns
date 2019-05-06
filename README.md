# ansible-dns

Repo permettant la configuration du fichier /etc/hosts | /etc/hostname | /etc/resolv.conf.  
Lors de la réinstallation d'un vps ssd avec OVH un mot de passe root provisoire est donné.  
Grâce à celui-ci nous allons pouvoir pousser les configurations via ansible facilement.  

ansible-playbook -i clients.ini plays/setup-all.yml -k root@1.2.3.4 
