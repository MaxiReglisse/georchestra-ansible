Adding X509 cert and Active Directory authentification to georchestra-ansible (geOrchestra-15.12)
=================================================================================================

geOrchestra-ansible proposes a simple ansible playbook to deploy a fullblown geOrchestra SDI instance.

original version is provided by LandryB : https://github.com/landryb/georchestra-ansible

Using this branch :

1) You will be able to authenticate users of your geOrchestra instance with an Active Directory.  
Look particularly the saslauth.yml file (https://github.com/MaxiReglisse/georchestra-ansible/blob/devel/roles/openldap/tasks/saslauth.yml).  
You will need to import AD users in geOrchestra LDAP with ad2ldap_sync.py. The saslauthd and slapd daemons will be configured with files provided in the openldap templates directory.

    roles/openldap/
    ├── handlers
    │   └── main.yml
    ├── tasks
    │   ├── clean.yml
    │   ├── main.yml
    │   └── saslauth.yml
    └── templates
        ├── ad2ldap_sync.py.j2
        ├── cn-config.ldif.j2
        ├── dot.ldap.conf.j2
        ├── ldap.conf.j2
        ├── saslauthd.conf.j2
        ├── saslauthd.j2
        └── slapd.conf.j2


2) Your geOrchestra server can use a x509 certificate provided by an official Certificate Authority.  
Take a look at the x509.yml file  (https://github.com/MaxiReglisse/georchestra-ansible/blob/devel/roles/apache/tasks/x509.yml) and 
organize public and private keys in the templates directory like that :

    roles/apache/templates
    ├── apache2
    │   ├── cert-xxxxx-georchestra.mydomain.org.pem.j2
    │   ├── chain-xxxxx-georchestra.mydomain.org.pem.j2
    │   ├── georchestra.conf.j2
    │   ├── georchestra.georchestra.mydomain.org.key.j2
    │   └── georchestra-x509.conf.j2
    ├── common.conf.j2
    ├── georchestra.j2
    └── global.conf.j2


