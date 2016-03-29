Adding X509 cert and Active Directory authentification to georchestra-ansible (geOrchestra-15.12)
=================================================================================================

geOrchestra-ansible proposes a simple ansible playbook to deploy a fullblown geOrchestra SDI instance.

original version is provided by LandryB : https://github.com/landryb/georchestra-ansible

Using this branch :

1) you will be able to authenticate users of your geOrchestra instance with an Active Directory.
look particularly https://github.com/MaxiReglisse/georchestra-ansible/blob/devel/roles/openldap/tasks/saslauth.yml

2) your geOrchestra server can use a x509 certificate provided by a Certificate Authority.
everything is here : https://github.com/MaxiReglisse/georchestra-ansible/blob/devel/roles/apache/tasks/x509.yml

