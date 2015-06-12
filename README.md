ansible-solr-5
===============

Ansible role to install single or multiple instances of Apache Solr 5.x for Ubuntu/Debian. Each instance will have its own init script _/etc/init.d/solr_instance_name_ and data directory _/var/log/solr_instance_name_.


Role Variables
--------------

* ######solr_instance_name
Instance name. Must be unique if you are using multiple instances on the same server.

* ######solr_home_parent & solr_home
Directory where the base solr_home directory will be kept. This base directory will only be used to create the instances and will not be a running instance by itself (Can be removed later).

* ######solr_version
Solr version to download and install. Default is 5.2.0.

* ######solr_dl_url
Download URL for Solr.

* ######solr_user
System user that the Solr instance(s) will be running as. Default is solr.

* ######solr_port
Listening port for the Solr instance. Default is 8983.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: solr, solr_instance_name: solr1x, solr_port:8985  }
         - { role: solr, solr_instance_name: solr2y, solr_port:8986  }
         - { role: solr, solr_instance_name: solr3z, solr_port:8987  }
