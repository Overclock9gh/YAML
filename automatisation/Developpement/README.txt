I. Liste des fichiers
---------------------
dnsv2.yml		Fichier d'automatisation de la configuration du serveur DNS
ipv6v2.yml		Fichier d'automatisation de la configuration IPV6
nfsv2.yml		Fichier d'automatisation de la configuration du serveur NFS
security.yml		Fichier d'automatisation de la configuration de la sécurité des serveurs
syslogv2.yml		Fichier d'automatisation de la configuration du serveur Syslog

Les fichiers sont exécutés par la commande "ansible-playbook /Chemin/Du/Fichier.yml".


II. Explications
----------------
A. Préparations

1. Sécurité
Il faut exécuter le playbook "security.yml" qui désactive 
le pare-feu & SELinux pour pouvoir établir la communication
et le bon fonctionnement du travail. 

B. Actions

2. Configurations
Par la suite, le fichier de configuration IPV6 s'occupera 
de donner les adresses nécessaires. Le reste configure 
chaque serveur comme expliqué précisement dans les commentaires
de chaque fichier.
 
Hierarchie & ordre d'exécution

	              |------------------|        
                      |    security.yml  |
                      |------------------|       
                               |                             
                               |                
                      |------------------|         
                      |    ipv6v2.yml    |
                     /|------------------|\            
                    /          |           \                  
                   /           |            \                   
|------------------|  |------------------|  |------------------|
|     dnsv2.yml    |->|   syslogv2.yml   |->|     nfsv2.yml    |
|------------------|  |------------------|  |------------------|
