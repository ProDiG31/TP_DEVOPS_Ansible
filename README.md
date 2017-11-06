TP_DEVOPS_Ansible 

Romain DUCROS - 06/11/2017

Creer 3 containers à partir de l'image registry.mrzee.fr/ynov/ssh-server:0.1

$> docker run -d --name="ssh-server-1" registry.mrzee.fr/ynov/ssh-server:0.1 
$> docker run -d --name="ssh-server-2" registry.mrzee.fr/ynov/ssh-server:0.1
$> docker run -d --name="ssh-server-3" registry.mrzee.fr/ynov/ssh-server:0.1

Ajouter les adresses ip des container dans le fichier hosts dans le dossier /etc/ansible/ :

[SSH-servers]
{{@ip  du container ssh-server-1}}
{{@ip  du container ssh-server-2}}
{{@ip  du container ssh-server-3}} 

Executer la commande 

$>ansible-playbook playbook.yml
