:is-up-to-date: True

.. _system-administrators:

#####################
System Administrators
#####################

This guide is intended to provide system administrators with the information and access to the tools they need to install and maintain Crafter CMS components.

*******************
System Requirements
*******************
+------------------+-----------------------------------+-----------------------------------------+
|| Parameter Name  || Description                      || Prerequisites                          |
+==================+===================================+=========================================+
|| Crafter Studio  || Content authoring server         || Java 1.8                               |
||                 ||                                  || 4+ Gig of memory to JVM                |
+------------------+-----------------------------------+-----------------------------------------+
|| Crafter Engine  || Content delivery server          || Java 1.8                               |
||                 ||                                  || 2+ Gig of memory to JVM                |
+------------------+-----------------------------------+-----------------------------------------+
|| Crafter Profile || User profile and attribute store || Java 1.8                               |
||                 || (Optional component)             || MongoDB 3+ (included in the bundle)    |
||                 ||                                  || 1+ Gig of memory to JVM                |
+------------------+-----------------------------------+-----------------------------------------+
|| Crafter Social  || User Generated Content server    || Java 1.8                               |
||                 || (Optional component)             || MongoDB 3+ (included in the bundle)    |
||                 ||                                  || 1+ Gig of memory to JVM                |
+------------------+-----------------------------------+-----------------------------------------+

* See :ref:`supported platforms<requirements_supported_platforms>` for a detailed list and description of supported components.

.. note:: Crafter CMS is not yet compatible with Java 1.9. We are working on updating our code to make sure we are 100% compatible with the newest Java version.


**********
Activities
**********

.. toctree::
   :maxdepth: 1
   :titlesonly:

   activities/installing-and-verifying-prereq.rst
   activities/backup-and-recovery.rst
   activities/clustering.rst
   activities/configure-solrcloud-for-crafter.rst
   activities/logging.rst
   activities/production-environment-setup.rst
   activities/reindexing-content.rst
   activities/reindexing-content-in-prod.rst
   activities/troubleshooting.rst
   activities/security/randomize-admin-passwd.rst
   activities/security/configure-studio-security.rst
   activities/kubernetes/simple-kubernetes-deployment.rst

*********************
Upgrading Crafter CMS
*********************

.. toctree::
   :maxdepth: 1
   :titlesonly:

   upgrade/upgrading-to-craftercms-3-1-0.rst
   upgrade/index.rst

*********
Authoring
*********

.. toctree::
   :maxdepth: 1
   :titlesonly:

   activities/authoring/authoring-env-performance-tuning.rst
   activities/authoring/change-hosts-ports-on-your-auth-install.rst
   activities/authoring/staging-env.rst
   activities/authoring/setup-authoring-using-aws-ami.rst
   activities/sync-studio-database-with-repo.rst

********
Delivery
********

.. toctree::
   :maxdepth: 1
   :titlesonly:

   activities/delivery/change-hosts-ports-on-your-delivery-install.rst
   activities/delivery/configure-apache-vhost.rst
   activities/delivery/setup-site-for-delivery.rst
   activities/delivery/setup-serverless-site.rst
   activities/delivery/setup-delivery-using-aws-ami.rst

*************************
Subsystems Administration
*************************

===============
Crafter Commons
===============

.. toctree::
   :maxdepth: 1
   :titlesonly:

   commons/encryption-tool.rst


================
Crafter Deployer
================

.. toctree::
   :maxdepth: 1
   :titlesonly:

   deployer/admin-guide.rst
   deployer/debugging-deployer-issues.rst


==============
Crafter Engine
==============

.. toctree::
   :maxdepth: 1
   :titlesonly:

   engine/configure-engine-multi-tenancy.rst
   engine/configure-engine-single-tenant.rst
   engine/turning-off-show-error.rst


===============
Crafter Profile
===============

.. toctree::
   :maxdepth: 1
   :titlesonly:

   profile/index.rst
   profile/admin/index.rst


==============
Crafter Search
==============

.. toctree::
   :maxdepth: 1
   :titlesonly:

   search/index.rst


==============
Crafter Social
==============

.. toctree::
   :maxdepth: 1
   :titlesonly:

   social/index.rst
   social/admin/index.rst


==============
Crafter Studio
==============

.. toctree::
   :maxdepth: 1
   :titlesonly:

   studio/changing-the-studio-logo.rst
   studio/studio-configuration-overrides.rst
   studio/debugging-publishing-issues.rst
   studio/debugging-upgrade-issues.rst
   studio/create-site-with-link-to-remote-repo.rst
   studio/session-timeout-settings.rst
