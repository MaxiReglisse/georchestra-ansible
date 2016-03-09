geOrchestra-ansible

A simple ansible playbook to deploy a fullblown geOrchestra SDI instance.

la version originale est ici : https://github.com/landryb/georchestra-ansible

cette branche prend en charge :

1: l'utilisation d'un certificat X509 pour le serveur geOrchestra
voir roles/apache/tasks/x509.yml
x509.yml est appelé par roles/apache/tasks/main.yml

2: l'authentification Active Directory des utilisateurs
voir roles/openldap/tasks/saslauth.yml
saslauth.yml est appelé par roles/openldap/tasks/main.yml
