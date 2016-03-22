Adding X509 cert and Active Directory authentification to georchestra-ansible (geOrchestra-15.12)
=================================================================================================

geOrchestra-ansible proposes a simple ansible playbook to deploy a fullblown geOrchestra SDI instance.

la version originale est ici : https://github.com/landryb/georchestra-ansible

cette branche prend en charge :

1: l'utilisation d'un certificat X509 pour le serveur geOrchestra.  
voir la tache x509 dans https://github.com/MaxiReglisse/georchestra-ansible/blob/devel/roles/apache/tasks/x509.yml  
x509.yml est appelé par roles/apache/tasks/main.yml

2: l'authentification Active Directory des utilisateurs, basée sur l'utilisation de saslauthd.   
voir la tache saslauth dans https://github.com/MaxiReglisse/georchestra-ansible/blob/devel/roles/openldap/tasks/saslauth.yml  
saslauth.yml est appelé par roles/openldap/tasks/main.yml

