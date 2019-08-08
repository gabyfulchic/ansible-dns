# ansible-dns

### Ansible.cfg
Afin d'éviter les arguments de masse sur la commande ansible-playbook lorsque qu'il y'a  
redondance sur le port ssh et l'utilisateur à utiliser par exemple, on peut configurer  
le fichier **ansible.cfg** avec un ***remote_user***=votre_user, ***remote_port***=votre_port,  
***inventory***=/path/to/votre/hostfile, ***ask_pass***=True, ***private_key_file***=/path/to/votre/keyfile !!  
Cela permettra d'éviter bcp d'arguments que je présente ci-dessous !!  
  
Et évidemment, il vous faudra :
```ruby 
cp your_ansible.cfg /etc/ansible/ansible.cfg
```

### OVH VPS
Repo permettant la configuration du fichier /etc/hosts | /etc/hostname | /etc/resolv.conf.  
Lors de la réinstallation d'un vps ssd avec OVH un mot de passe root provisoire est donné.  
Grâce à celui-ci nous allons pouvoir pousser les configurations via ansible facilement.  

```ruby
ansible-playbook -i clients.ini plays/setup-all.yml -k root@1.2.3.4
```   

### Azure compute / GCP compute / AWS EC2
Pour les autres Cloud Providers il suffira de renseigner la clé publique sur leur interface  
graphique respective. C'est plus secure et demande une intéraction en moins.  

```ruby
ansible-playbook -i clients.ini plays/setup-all.yml --private-key='/private/.ssh/key' azureuser/gcpuser/awsuser@1.2.3.4
```  


