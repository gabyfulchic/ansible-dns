# ansible-dns

### OVH VPS
Repo permettant la configuration du fichier /etc/hosts | /etc/hostname | /etc/resolv.conf.  
Lors de la réinstallation d'un vps ssd avec OVH un mot de passe root provisoire est donné.  
Grâce à celui-ci nous allons pouvoir pousser les configurations via ansible facilement.  

``` ansible-playbook -i clients.ini plays/setup-all.yml -k root@1.2.3.4 ```   

### Azure compute / GCP compute / AWS EC2
Pour les autres Cloud Providers il suffira de renseigner la clé publique sur leur interface  
graphique respective. C'est plus secure et demande une intéraction en moins.  

``` ansible-playbook -i clients.ini plays/setup-all.yml --private-key='/private/.ssh/key' azureuser/gcpuser/awsuser@1.2.3.4 ```  


