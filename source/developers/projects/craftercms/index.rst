:is-up-to-date: True

.. index:: Projects; Crafter CMS

.. _crafter-cms:

###########
Crafter CMS
###########

This project is the parent project that builds everything and prepares a deployable bundle and a developer's environment.

***********
Source Code
***********

Crafter CMS's source code is managed in GitHub: https://github.com/craftercms/craftercms

*************
Documentation
*************

===============
Getting Started
===============

To get started, please review: https://github.com/craftercms/craftercms/blob/master/README.md

For every Crafter CMS repository, there are two long-running branches:

    * ``develop``: this is where development activities happen, and this branch is not meant to be stable
    * ``master``: this is stable and deployable

If you're building a deployable Crafter CMS bundle, you'll need to clone the master branch:

    .. code-block:: bash

        git clone https://github.com/craftercms/craftercms.git

OR

If you would like to contribute to Crafter CMS, to build a developer's environment, you'll need to to clone the develop branch:

    .. code-block:: bash

        git clone https://github.com/craftercms/craftercms.git -b develop

For more information on Crafter CMS Git Workflow, please review: https://github.com/craftercms/craftercms/blob/master/GIT_WORKFLOW.md

====================
More Advanced Topics
====================

Crafter CMS has two environments, the Authoring Environment and the Delivery Environment.

The authoring environment provides all the content management services, enabling authoring, managing and publishing of all content.  It provides a comprehensive set of user-friendly features for managing and optimizing your experiences.

The delivery environment provides content delivery services.  It consumes content published from your authoring environment and provides developers with the foundation for quickly building high-performance, flexible experiences.

In this section we will be discussing the scripts for the authoring and delivery environments.

------------------------------------------
Authoring and Delivery Environment Scripts
------------------------------------------

The Crafter CMS Authoring and Delivery scripts will help you on the basic startup and shutdown of the services needed to run a healthy *Authoring environment* and *Delivery environment* with the following scripts:

+-------------------------+------------------------------------------------------------------------+
|| **Script**             || ``crafter.sh``                                                        |
+-------------------------+------------------------------------------------------------------------+
|| **Description**        || Main Script to start and stop all needed Services to have a           |
||                        || functional Crafter CMS *Authoring/Delivery Environment*               |
+-------------------------+------------------------------------------------------------------------+
|| **Synopsis**           || ``crafter.sh start|stop|debug|help``                                  |
+-------------------------+------------------------------------------------------------------------+
|| **Arguments**          || * ``start [withMongoDB] [withSolr] [skipElasticsearch] [skipMongoDB]``|
||                        ||   Starts all Crafter CMS services in this order                       |
||                        ||   Crafter Deployer, Elasticsearch, Apache Tomcat                      |
||                        ||   If withMongoDB is specified MongoDB will be started.                |
||                        ||   If withSolr is specified Solr will be started.                      |
||                        ||   If skipElasticsearch is specified Elasticsearch will not be started.|
||                        ||   If skipMongoDB is specified MongoDB will not bestarted even if the  |
||                        ||   Crafter Profile war is present.                                     |
||                        || * ``stop``  Stops all Crafter CMS services in the same order as       |
||                        ||    they start.                                                        |
||                        || * ``debug [withMongoDB] [withSolr] [skipElasticsearch] [skipMongoDB]``|
||                        ||   Starts all Crafter CMS services with the JAVA remote                |
||                        ||   debug port 5000 for Crafter Deployer, 5005 for Solr and 8000        |
||                        ||   for Apache Tomcat for the *Authoring Environment*                   |
||                        ||   Starts all Crafter CMS services with the JAVA remote debug port     |
||                        ||   5001 for Crafter Deployer, 5006 for Solr and 9000 for Apache        |
||                        ||   Tomcat for the *Delivery Environment*                               |
||                        ||   If withMongoDB is specified MongoDB will be started.                |
||                        ||   If withSolr is specified Solr will be started.                      |
||                        ||   If skipElasticsearch is specified Elasticsearch will not be started.|
||                        ||   If skipMongoDB is specified MongoDB will not bestarted even if the  |
||                        ||   Crafter Profile war is present.                                     |
||                        || * ``status`` Prints the status of Solr, Crafter Deployer and          |
||                        ||    Crafter Studio (uptime, process id and version if applicable)      |
||                        || * ``help``  Prints all options available                              |
||                        || * ``start_deployer``  Starts Deployer                                 |
||                        || * ``stop_deployer``  Stops Deployer                                   |
||                        || * ``debug_deployer``  Starts Deployer in debug mode                   |
||                        || * ``start_solr``  Starts Solr                                         |
||                        || * ``stop_solr``  Stops Solr                                           |
||                        || * ``debug_solr``  Starts Solr in debug mode                           |
||                        || * ``start_elasticsearch``  Starts Elasticsearch                       |
||                        || * ``stop_elasticsearch``  Stops Elasticsearch                         |
||                        || * ``debug_elasticsearch``  Starts Elasticsearch in debug mode         |
||                        || * ``start_tomcat``  Starts Apache Tomcat                              |
||                        || * ``stop_tomcat``  Stops Apache Tomcat                                |
||                        || * ``debug_tomcat``  Starts Apache Tomcat in debug mode                |
||                        || * ``start_mongodb``  Starts MongoDB                                   |
||                        || * ``stop_mongodb``  Stops MongoDB                                     |
||                        || * ``status_engine``  Prints the status of Crafter Engine              |
||                        || * ``status_studio``  Prints the status of Crafter Studio              |
||                        || * ``status_profile``  Prints the status of Crafter Profile            |
||                        || * ``status_social``  Prints the status of Crafter Social              |
||                        || * ``status_deployer``  Prints the status of Crafter Deployer          |
||                        || * ``status_search``  Prints the status of Crafter Search              |
||                        || * ``status_solr``  Prints the status of Solr                          |
||                        || * ``status_elasticsearch``  Prints the status of Elasticsearch        |
||                        || * ``status_mariadb``  Prints the status of MariaDb                    |
||                        || * ``status_mongodb``  Prints the status of MongoDB                    |
||                        || * ``backup <name>``  Perform a backup of all data                     |
||                        || * ``restore <file>``  Perform a restore of all data                   |
+-------------------------+------------------------------------------------------------------------+

+-------------------------+----------------------------------------------------------------------+
|| **Synopsis**           || ``startup.sh``                                                      |
+-------------------------+----------------------------------------------------------------------+
|| **Description**        || Starts all needed Services to have a functional                     |
||                        || Crafter CMS *Authoring/Delivery Environment*                        |
+-------------------------+----------------------------------------------------------------------+

+-------------------------+----------------------------------------------------------------------+
|| **Synopsis**           || ``shutdown.sh``                                                     |
+-------------------------+----------------------------------------------------------------------+
|| **Description**        || Stops all needed Services to have a functional                      |
||                        || Crafter CMS *Authoring/Delivery Environment*                        |
+-------------------------+----------------------------------------------------------------------+

+-------------------------+----------------------------------------------------------------------+
|| **Synopsis**           || ``debug.sh``                                                        |
+-------------------------+----------------------------------------------------------------------+
|| **Description**        || Starts all needed Services to have a functional                     |
||                        || Crafter CMS *Authoring/Delivery Environment* with the JAVA remote   |
||                        || debug ports open and listening port 5000/5001 for Crafter Deployer, |
||                        || 5005/5006 for Solr and 8000/9000 for Apache Tomcat                  |
+-------------------------+----------------------------------------------------------------------+

+-------------------------+----------------------------------------------------------------------+
|| **Script**             || ``deployer.sh``                                                     |
+-------------------------+----------------------------------------------------------------------+
|| **Description**        || Script located in *$CRAFTER_HOME/crafter-deployer* which will       |
||                        || start,stop Crafter Deployer for the *Authoring/Delivery* environment|
+-------------------------+----------------------------------------------------------------------+
|| **Synopsis**           || ``deployer.sh start|stop|debug|help``                               |
+-------------------------+----------------------------------------------------------------------+
|| **Arguments**          || * ``start`` Starts all Crafter CMS services in this order           |
||                        ||    Crafter Deployer, Elasticsearch, Apache Tomcat                   |
||                        || * ``stop``  Stops all Crafter CMS services in the same order as     |
||                        ||    they start.                                                      |
||                        || * ``debug`` Start all Crafter CMS services with the JAVA remote     |
||                        ||    debug port 5000 for Crafter Deployer, 5005 for Solr and 8000     |
||                        ||    for Apache Tomcat for the *Authoring Environment*                |
||                        ||    Starts all Crafter CMS services with the JAVA remote debug port  |
||                        ||    5001 for Crafter Deployer, 5006 for Solr and 9000 for Apache     |
||                        ||    Tomcat for the *Delivery Environment*                            |
||                        || * ``help``  Prints script help                                      |
+-------------------------+----------------------------------------------------------------------+

Here are the location environment variables used by ``crafter.sh``:

+--------------------------+---------------------------------------------------------------------+
|| Variable Name           || Description                                                        |
||                         +---------------------------------------------------------------------+
||                         || Default Value                                                      |
+==========================+=====================================================================+
|| CRAFTER_HOME            || Crafter CMS *Authoring/Delivery* path                              |
||                         +---------------------------------------------------------------------+
||                         || {Crafter-CMS-install-directory}/crafter-{env}/bin                  |
+--------------------------+---------------------------------------------------------------------+
|| CRAFTER_LOGS_DIR        || Crafter CMS logs file path                                         |
||                         +---------------------------------------------------------------------+
||                         || $CRAFTER_HOME/logs                                                 |
+--------------------------+---------------------------------------------------------------------+
|| CRAFTER_DATA_DIR        || Crafter CMS data file path                                         |
||                         +---------------------------------------------------------------------+
||                         || $CRAFTER_HOME/data                                                 |
+--------------------------+---------------------------------------------------------------------+
|| CRAFTER_TEMP_DIR        || Crafter CMS temporary directory path                               |
||                         +---------------------------------------------------------------------+
||                         || $CRAFTER_HOME/temp                                                 |
+--------------------------+---------------------------------------------------------------------+

Here are the environment variables used for hosts and ports in ``crafter(.sh/bat)``:

+--------------------------+---------------------------------------------------------------------+
|| Hosts and Ports         || Description                                                        |
|| Variable Name           +---------------------------------------------------------------------+
||                         || Default Value                                                      |
+==========================+=====================================================================+
|| MAIL_HOST               || Crafter CMS mail host                                              |
||                         +---------------------------------------------------------------------+
||                         || localhost                                                          |
+--------------------------+---------------------------------------------------------------------+
|| MAIL_PORT               || Crafter CMS mail port                                              |
||                         +---------------------------------------------------------------------+
||                         || 25                                                                 |
+--------------------------+---------------------------------------------------------------------+
|| SOLR_HOST               || Solr host                                                          |
||                         +---------------------------------------------------------------------+
||                         || localhost                                                          |
+--------------------------+---------------------------------------------------------------------+
|| SOLR_PORT               || Solr port                                                          |
||                         +---------------------------------------------------------------------+
||                         || 8694                                                               |
+--------------------------+---------------------------------------------------------------------+
|| ES_HOST                 || Elasticsearch host                                                 |
||                         +---------------------------------------------------------------------+
||                         || localhost                                                          |
+--------------------------+---------------------------------------------------------------------+
|| ES_PORT                 || Elasticsearch port                                                 |
||                         +---------------------------------------------------------------------+
||                         || 9201                                                               |
+--------------------------+---------------------------------------------------------------------+
|| DEPLOYER_HOST           || Deployer host                                                      |
||                         +---------------------------------------------------------------------+
||                         || localhost                                                          |
+--------------------------+---------------------------------------------------------------------+
|| DEPLOYER_PORT           || Deployer port                                                      |
||                         +---------------------------------------------------------------------+
||                         || 9201                                                               |
+--------------------------+---------------------------------------------------------------------+
|| MONGODB_HOST            || MongoDB host                                                       |
||                         +---------------------------------------------------------------------+
||                         || localhost                                                          |
+--------------------------+---------------------------------------------------------------------+
|| MONGODB_PORT            || MongoDB port                                                       |
||                         +---------------------------------------------------------------------+
||                         || 27020                                                              |
+--------------------------+---------------------------------------------------------------------+
|| MARIADB_HOST            || MariaDb host                                                       |
||                         +---------------------------------------------------------------------+
||                         || 127.0.0.1                                                          |
+--------------------------+---------------------------------------------------------------------+
|| MARIADB_PORT            || MariaDb port                                                       |
||                         +---------------------------------------------------------------------+
||                         || 33306                                                              |
+--------------------------+---------------------------------------------------------------------+
|| TOMCAT_HOST             || Tomcat host                                                        |
||                         +---------------------------------------------------------------------+
||                         || localhost                                                          |
+--------------------------+---------------------------------------------------------------------+
|| TOMCAT_HTTP_PORT        || Tomcat Http port                                                   |
||                         +---------------------------------------------------------------------+
||                         || 8080                                                               |
+--------------------------+---------------------------------------------------------------------+
|| TOMCAT_HTTPS_PORT       || Tomcat SSL (https) port                                            |
||                         +---------------------------------------------------------------------+
||                         || 8443                                                               |
+--------------------------+---------------------------------------------------------------------+
|| TOMCAT_AJP_PORT         || Tomcat AJP port                                                    |
||                         +---------------------------------------------------------------------+
||                         || 8009                                                               |
+--------------------------+---------------------------------------------------------------------+
|| TOMCAT_SHUTDOWN_PORT    || Tomcat shutdown port                                               |
||                         +---------------------------------------------------------------------+
||                         || 8005                                                               |
+--------------------------+---------------------------------------------------------------------+

Here are the environment variables used for URLs in ``crafter(.sh/bat)``:

+--------------------------+---------------------------------------------------------------------+
|| URLs                    || Description                                                        |
|| Variable Name           +---------------------------------------------------------------------+
||                         || Default Value                                                      |
+==========================+=====================================================================+
|| SOLR_URL                || Solr URL                                                           |
||                         +---------------------------------------------------------------------+
||                         || "http://$SOLR_HOST:$SOLR_PORT/solr"                                |
+--------------------------+---------------------------------------------------------------------+
|| ES_URL                  || Elasticsearch URL                                                  |
||                         +---------------------------------------------------------------------+
||                         || "http://$ES_HOST:$ES_PORT"                                         |
+--------------------------+---------------------------------------------------------------------+
|| DEPLOYER_URL            || Crafter Deployer URL                                               |
||                         +---------------------------------------------------------------------+
||                         || "http://$DEPLOYER_HOST:$DEPLOYER_PORT"                             |
+--------------------------+---------------------------------------------------------------------+
|| STUDIO_URL              || Crafter Studio URL                                                 |
||                         +---------------------------------------------------------------------+
||                         || "http://$TOMCAT_HOST:$TOMCAT_HTTP_PORT/studio"                     |
+--------------------------+---------------------------------------------------------------------+
|| ENGINE_URL              || Crafter Engine URL                                                 |
||                         +---------------------------------------------------------------------+
||                         || "http://$TOMCAT_HOST:$TOMCAT_HTTP_PORT/studio"                     |
+--------------------------+---------------------------------------------------------------------+
|| SEARCH_URL              || Crafter Search URL                                                 |
||                         +---------------------------------------------------------------------+
||                         || "http://$TOMCAT_HOST:$TOMCAT_HTTP_PORT/crafter-search"             |
+--------------------------+---------------------------------------------------------------------+
|| PROFILE_URL             || Crafter Profile URL                                                |
||                         +---------------------------------------------------------------------+
||                         || "http://$TOMCAT_HOST:$TOMCAT_HTTP_PORT/crafter-profile"            |
+--------------------------+---------------------------------------------------------------------+
|| SOCIAL_URL              || Crafter Social URL                                                 |
||                         +---------------------------------------------------------------------+
||                         || "http://$TOMCAT_HOST:$TOMCAT_HTTP_PORT/crafter-social"             |
+--------------------------+---------------------------------------------------------------------+

Here are the environment variables used for Java options in ``crafter.sh``:

+--------------------------+---------------------------------------------------------------------+
|| Java options            || Description                                                        |
|| Variable Name           +---------------------------------------------------------------------+
||                         || Default Value                                                      |
+==========================+=====================================================================+
|| SOLR_JAVA_OPTS          || Solr Java options                                                  |
||                         +---------------------------------------------------------------------+
||                         || "-server -Xss1024K -Xmx1G"                                         |
+--------------------------+---------------------------------------------------------------------+
|| ES_JAVA_OPTS            || Elasticsearch Java options                                         |
||                         +---------------------------------------------------------------------+
||                         || "-server -Xss1024K -Xmx1G"                                         |
+--------------------------+---------------------------------------------------------------------+
|| DEPLOYER_JAVA_OPTS      || Deployer Java options                                              |
||                         +---------------------------------------------------------------------+
||                         || "-server -Xss1024K -Xmx1G"                                         |
+--------------------------+---------------------------------------------------------------------+
|| CATALINA_OPTS           || Tomcat options                                                     |
||                         +---------------------------------------------------------------------+
||                         || "-server -Xss1024K -Xms1G -Xmx4G"                                  |
+--------------------------+---------------------------------------------------------------------+

Here are the environment variables used for Tomcat in ``crafter.sh``:

+--------------------------+---------------------------------------------------------------------+
|| Tomcat                  || Description                                                        |
|| Variable Name           +---------------------------------------------------------------------+
||                         || Default Value                                                      |
+==========================+=====================================================================+
|| CATALINA_HOME           || Apache Tomcat files path                                           |
||                         +---------------------------------------------------------------------+
||                         || $CRAFTER_HOME/apache-tomcat                                        |
+--------------------------+---------------------------------------------------------------------+
|| CATALINA_PID            || Tomcat process id file save path                                   |
||                         +---------------------------------------------------------------------+
||                         || $CATALINA_HOME/tomcat.pid                                          |
+--------------------------+---------------------------------------------------------------------+
|| CATALINA_LOGS_DIR       || Tomcat file logs path                                              |
||                         +---------------------------------------------------------------------+
||                         || $CRAFTER_LOGS_DIR/tomcat                                           |
+--------------------------+---------------------------------------------------------------------+
|| CATALINA_OUT            || Tomcat main log file                                               |
||                         +---------------------------------------------------------------------+
||                         || $CATALINA_LOGS_DIR/catalina.out                                    |
+--------------------------+---------------------------------------------------------------------+
|| CATALINA_TMPDIR         || Tomcat temporary directory                                         |
||                         +---------------------------------------------------------------------+
||                         || $CRAFTER_TEMP_DIR/tomcat                                           |
+--------------------------+---------------------------------------------------------------------+
|| CRAFTER_APPLICATION_LOGS|| Crafter application log files path                                 |
||                         +---------------------------------------------------------------------+
||                         || $CATALINA_LOGS_DIR                                                 |
+--------------------------+---------------------------------------------------------------------+

Here are the environment variables used for Elasticsearch in ``crafter.sh``:

+--------------------------+---------------------------------------------------------------------+
|| Elasticsearch           || Description                                                        |
|| Variable Name           +---------------------------------------------------------------------+
||                         || Default Value                                                      |
+==========================+=====================================================================+
|| ES_HOME                 || Elasticsearch home directory                                       |
||                         +---------------------------------------------------------------------+
||                         || $CRAFTER_BIN_DIR/elasticsearch/bin                                 |
+--------------------------+---------------------------------------------------------------------+
|| ES_INDEXES_DIR          || Elasticsearch indexes directory                                    |
||                         +---------------------------------------------------------------------+
||                         || $CRAFTER_DATA_DIR/indexes-es                                       |
+--------------------------+---------------------------------------------------------------------+
|| ES_LOGS_DIR             || Elasticsearch log files directory                                  |
||                         +---------------------------------------------------------------------+
||                         || $CRAFTER_LOGS_DIR/logs/elasticsearch                               |
+--------------------------+---------------------------------------------------------------------+
|| ES_PID                  || Elasticsearch process Id                                           |
||                         +---------------------------------------------------------------------+
||                         || $ES_HOME/elasticsearch.pid                                         |
+--------------------------+---------------------------------------------------------------------+

Here are the environment variables used for Solr in ``crafter.sh``:

+--------------------------+---------------------------------------------------------------------+
|| Solr                    || Description                                                        |
|| Variable Name           +---------------------------------------------------------------------+
||                         || Default Value                                                      |
+==========================+=====================================================================+
|| SOLR_HOME               || Solr home directory                                                |
||                         +---------------------------------------------------------------------+
||                         || $CRAFTER_BIN_DIR/solr/server/solr                                  |
+--------------------------+---------------------------------------------------------------------+
|| SOLR_INDEXES_DIR        || Solr indexes directory                                             |
||                         +---------------------------------------------------------------------+
||                         || $CRAFTER_DATA_DIR/indexes                                          |
+--------------------------+---------------------------------------------------------------------+
|| SOLR_LOGS_DIR           || Solr log files directory                                           |
||                         +---------------------------------------------------------------------+
||                         || $CRAFTER_LOGS_DIR/solr                                             |
+--------------------------+---------------------------------------------------------------------+
|| SOLR_PID                || Solr process id file                                               |
||                         +---------------------------------------------------------------------+
||                         || $SOLR_INDEXES_DIR/solr.pid                                         |
+--------------------------+---------------------------------------------------------------------+


Here are the environment variables used for the Deployer in ``crafter.sh``:

+--------------------------+---------------------------------------------------------------------+
|| Deployer                || Description                                                        |
|| Variable Name           +---------------------------------------------------------------------+
||                         || Default Value                                                      |
+==========================+=====================================================================+
|| DEPLOYER_HOME           || Crafter Deployer jar files path                                    |
||                         +---------------------------------------------------------------------+
||                         || $CRAFTER_HOME/crafter-deployer                                     |
+--------------------------+---------------------------------------------------------------------+
|| DEPLOYER_DATA_DIR       || Deployer data files directory                                      |
||                         +---------------------------------------------------------------------+
||                         || $CRAFTER_DATA_DIR/deployer                                         |
+--------------------------+---------------------------------------------------------------------+
|| DEPLOYER_LOGS_DIR       || Deployer log files directory                                       |
||                         +---------------------------------------------------------------------+
||                         || $CRAFTER_LOGS_DIR/deployer                                         |
+--------------------------+---------------------------------------------------------------------+
|| DEPLOYER_DEPLOYMENTS_DIR|| Deployer deployments files directory                               |
||                         +---------------------------------------------------------------------+
||                         || $CRAFTER_DATA_DIR/repos/sites                                      |
+--------------------------+---------------------------------------------------------------------+
|| DEPLOYER_SDOUT          || Deployer SDOUT path                                                |
||                         +---------------------------------------------------------------------+
||                         || $DEPLOYER_LOGS_DIR/crafter-deployer.out                            |
+--------------------------+---------------------------------------------------------------------+
|| DEPLOYER_PID            || Deployer process id file                                           |
||                         +---------------------------------------------------------------------+
||                         || $DEPLOYER_HOME/crafter-deployer.pid                                |
+--------------------------+---------------------------------------------------------------------+


Here are the environment variables used for MongoDB in ``crafter.sh``:

+--------------------------+---------------------------------------------------------------------+
|| MongoDB                 || Description                                                        |
|| Variable Name           +---------------------------------------------------------------------+
||                         || Default Value                                                      |
+==========================+=====================================================================+
|| MONGODB_HOME            || MongoDB files path                                                 |
||                         +---------------------------------------------------------------------+
||                         || $CRAFTER_BIN_DIR/mongodb                                           |
+--------------------------+---------------------------------------------------------------------+
|| MONGODB_PID             || MongoDB process id file save path                                  |
||                         +---------------------------------------------------------------------+
||                         || $MONGODB_DATA_DIR/mongod.lock                                      |
+--------------------------+---------------------------------------------------------------------+
|| MONGODB_DATA_DIR        || MongoDB data directory                                             |
||                         +---------------------------------------------------------------------+
||                         || $CRAFTER_DATA_DIR/mongodb                                          |
+--------------------------+---------------------------------------------------------------------+
|| MONGODB_LOGS_DIR        || MongoDB log files directory                                        |
||                         +---------------------------------------------------------------------+
||                         || $CRAFTER_LOGS_DIR/mongodb                                          |
+--------------------------+---------------------------------------------------------------------+

Here are the environment variables used for MariaDb in ``crafter.sh``:

+--------------------------+---------------------------------------------------------------------+
|| MariaDb                 || Description                                                        |
|| Variable Name           +---------------------------------------------------------------------+
||                         || Default Value                                                      |
+==========================+=====================================================================+
|| MARIADB_HOME            || MariaDb files path                                                 |
||                         +---------------------------------------------------------------------+
||                         || $CRAFTER_BIN_DIR/dbms                                              |
+--------------------------+---------------------------------------------------------------------+
|| MARIADB_DATA_DIR        || MariaDb data directory                                             |
||                         +---------------------------------------------------------------------+
||                         || $CRAFTER_DATA_DIR/db                                               |
+--------------------------+---------------------------------------------------------------------+
|| MARIADB_ROOT_PASSWD     || MariaDb root password                                              |
||                         +---------------------------------------------------------------------+
||                         ||                                                                    |
+--------------------------+---------------------------------------------------------------------+

Here are the environment variables used for Git in ``crafter(.sh/bat)``:

+--------------------------+---------------------------------------------------------------------+
|| Git                     || Description                                                        |
|| Variable Name           +---------------------------------------------------------------------+
||                         || Default Value                                                      |
+==========================+=====================================================================+
|| GIT_CONFIG_NOSYSTEM     || Ignore Git system wide configuration file                          |
||                         +---------------------------------------------------------------------+
||                         || true                                                               |
+--------------------------+---------------------------------------------------------------------+


Let's look at an example on how to start an authoring environment using the scripts we discussed above.  To start the authoring environment, go to your Crafter CMS install folder then run the following:

    .. code-block:: bash

        cd crafter-authoring
        ./startup.sh

What the above does is go to your authoring environment folder, then run the startup script.

To stop the authoring environment:

    .. code-block:: bash

        ./shutdown.sh

^^^^^^^^^^^^^
Other Scripts
^^^^^^^^^^^^^

For more information about Apache Tomcat, Solr, and Elasticsearch please refer to the following:

 * [Tomcat Script documentation](https://tomcat.apache.org/tomcat-8.5-doc/RUNNING.txt)
 * [Solr Script documentation](https://cwiki.apache.org/confluence/display/solr/Running+Solr)
 * [ElasticSEarch Script documentation](https://www.elastic.co/guide/en/elasticsearch/reference/current/starting-elasticsearch.html)


-------------------------------------------------
Gradle Authoring and Delivery Environment Scripts
-------------------------------------------------

As we have seen in the getting started section above, to run a gradle task, we run the following from the root of the project:

    .. code-block:: bash

       ./gradlew command [-Penv={env}] [-PmoduleName={module}]


Here's a list of commands (Gradle tasks) available:

+---------------+-------------------------------------------+--------------+-----------------+
|| Command      || Description                              || Env Options || Module Options |
|| ``command``  ||                                          || ``env``     || ``module``     |
+===============+===========================================+==============+=================+
|| init         || Clones Crafter CMS                       || - None      || - None         |
+---------------+-------------------------------------------+--------------+-----------------+
|| build        || Build a module or an entire              || authoring   || - None         |
||              || environment                              ||             || - studio       |
||              ||                                          ||             || - deployer     |
||              ||                                          ||             || - engine       |
||              ||                                          ||             || - search       |
||              ||                                          ||             || - social       |
||              ||                                          ||             || - profile      |
||              ||                                          ||             || - core         |
||              ||                                          ||             || - commons      |
||              ||                                          ||             || - studio-ui    |
||              ||                                          ||             || - plugin-maker |
||              ||                                          +--------------+                 |
||              ||                                          || delivery    ||                |
+---------------+-------------------------------------------+--------------+-----------------+
|| deploy       || Deploy a module or an entire             || authoring   || - None         |
||              || environment                              ||             || - studio       |
||              ||                                          ||             || - deployer     |
||              ||                                          ||             || - engine       |
||              ||                                          ||             || - search       |
||              ||                                          ||             || - social       |
||              ||                                          ||             || - profile      |
||              ||                                          +--------------+-----------------+
||              ||                                          || delivery    || - None         |
||              ||                                          ||             || - deployer     |
||              ||                                          ||             || - engine       |
||              ||                                          ||             || - search       |
||              ||                                          ||             || - social       |
||              ||                                          ||             || - profile      |
+---------------+-------------------------------------------+--------------+-----------------+
|| bundle       || Build a deployable and distributable     || authoring   || - None         |
||              || bundle                                   +--------------+                 |
||              ||                                          || delivery    ||                |
+---------------+-------------------------------------------+--------------+-----------------+
|| start        || Start Crafter CMS                        || authoring   || - None         |
||              ||                                          +--------------+                 |
||              ||                                          || delivery    ||                |
+---------------+-------------------------------------------+--------------+-----------------+
|| stop         || Stop Crafter CMS                         || authoring   || - None         |
||              ||                                          +--------------+                 |
||              ||                                          || delivery    ||                |
+---------------+-------------------------------------------+--------------+-----------------+
|| update       || Update a module or modules               || - None      || - None         |
||              ||                                          ||             || - studio       |
||              ||                                          ||             || - deployer     |
||              ||                                          ||             || - engine       |
||              ||                                          ||             || - search       |
||              ||                                          ||             || - social       |
||              ||                                          ||             || - profile      |
||              ||                                          ||             || - core         |
||              ||                                          ||             || - commons      |
||              ||                                          ||             || - studio-ui    |
||              ||                                          ||             || - plugin-maker |
+---------------+-------------------------------------------+--------------+-----------------+
|| upgrade      || Upgrades the installed Tomcat version,   || - None      || - None         |
||              || Solr scripts, etc, without deleting your ||             ||                |
||              || data then builds and deploys             ||             ||                |
+---------------+-------------------------------------------+--------------+-----------------+
|| selfupdate   || Updates the Crafter CMS project (gradle) || - None      || - None         |
+---------------+-------------------------------------------+--------------+-----------------+
|| clean        || Delete all compiled objects              || - None      || - None         |
+---------------+-------------------------------------------+--------------+-----------------+

.. note::

    * If you don't specify the ``env`` parameter, it means all environments (where applicable).
    * In the current version of Crafter CMS, some services run in the same Web container, and that implies the stopping/starting of one of these services will cause other services to stop/start as well.
    * The Gradle task property ``moduleName`` accepts one or multiple module/s, separated by commas like this: ``./gradlew build -PmoduleName=search,studio``


Let's see some examples of running Gradle tasks here.

^^^^^
BUILD
^^^^^

To build the authoring and delivery environments, run the following:

    .. code-block:: bash

       ./gradlew build

The Gradle task above will:

#. Delete any existing environments/module
#. Download Apache Tomcat, Elasticsearch, Apache Solr and MongoDB (check the Gradle section on how to specify a version for each component)
#. Build all Crafter CMS modules from the source (check the :ref:`git` section on how to update the source)
#. Create the environment folders and copy all needed resources

    - ``crafter-authoring``
    - ``crafter-delivery``

To build a module (all module options for task ``build`` are listed in the table above), run the following (we'll build the module *studio* in the example below):

    .. code-block:: bash

       ./gradlew build -PmoduleName=studio


To build an environment, run the following (we'll build the authoring environment in the example below:

    .. code-block:: bash

       ./gradlew build -Penv=authoring

^^^^^
START
^^^^^

To start an environment, run the following:

    .. code-block:: bash

       ./gradlew start [-Penv={env}]

What this does under the hood is:

    .. code-block:: bash

       cd crafter-{env}
       ./startup.sh

The options above will:

For the *Authoring Environment*:

* Start Apache tomcat on default ports (8080, 8009, 8005) [See :ref:`gradle-tasks` on how to change default ports]
* Start Elasticsearch on port 9201
* Start Crafter Deployer on port 9191

For the *Delivery Environment*:

* Start Apache tomcat on default ports (9080, 9009, 9005) [See :ref:`gradle-tasks` on how to change default ports]
* Start ElasticSEarch server on port 9202
* Start Crafter Deployer on port 9192

Here's an example starting an authoring environment:

    .. code-block:: bash

       ./gradlew start -Penv=authoring


^^^^
STOP
^^^^

To stop an environment, run the following:

    .. code-block:: bash

       ./gradlew stop [-Penv={env}]

What this does under the hood is:

    .. code-block:: bash

       cd crafter-{env}
       ./shutdown.sh


^^^^^^
BUNDLE
^^^^^^

The Gradle task ``bundle`` will build a deployable and distributable bundle of Crafter CMS for the authoring and/or delivery environments.  This will generate zip and tar files ready to be unarchived and run.

    .. code-block:: bash

       ./gradlew bundle [-Penv={env}] [-Pcrafter.bundle.archive={tar|zip}]

Archives will be saved as ``crafter-cms-authoring.tar`` and ``crafter-cms-authoring.zip`` for the *Authoring Environment* and ``crafter-cms-delivery.tar`` and ``crafter-cms-delivery.zip`` for the *Delivery Environment* in the ``bundles`` folder

Using the bundle task property ``crafter.bundle.archive`` lets you select what archive (tar or zip) will be generated, and the common task property ``env`` lets you select what environment (authoring or delivery) will be generated.

Let's look at an example using the two task properties mentioned above:

    .. code-block:: bash

        ./gradlew bundle -Penv=authoring -Pcrafter.bundle.archive=zip

The command above will generate an authoring zip bundle in the bundles folder named ``crafter-cms-authoring.zip``.  If the property ``crafter.bundle.archive`` is not specified, an authoring zip and tar file bundles will be generated.

There are four more gradle bundle tasks available for use aside from ``bundle``:

* ``delivery_bundle_tar`` - Bundles as a Tar file delivery environment
* ``delivery_bundle_zip`` - Bundles as a Zip file delivery environment
* ``authoring_bundle_tar`` - Bundles as a Tar file authoring environment
* ``authoring_bundle_zip`` - Bundles as a Zip file authoring environment

Here's an example using one of the above gradle task to generate an authoring zip bundle:

    .. code-block:: bash

        ./gradlew authoring_bundle_zip

.. _gradle-tasks:

^^^^^^^^^^^^
Gradle Tasks
^^^^^^^^^^^^

In the section above, we discussed some of the Gradle tasks used for building, starting, stopping and bundling our authoring and delivery environments.  To get more information about all tasks used, run the following:

    .. code-block:: bash

       ./gradlew tasks --all

Let's take a look at some examples of running a task.

downloadSolr
^^^^^^^^^^^^
Downloads the configured Solr version and also verifies that the war file is ok against a sha1 signature.

    .. code-block:: bash

       ./gradlew downloadSolr


downloadTomcat
^^^^^^^^^^^^^^
Downloads the configured Tomcat version and also verifies that the zip file is ok against a sha1 signature.

    .. code-block:: bash

       ./gradlew downloadTomcat



.. _common-task-properties:

Common Task Properties
^^^^^^^^^^^^^^^^^^^^^^

Aside from the tasks that we can run, there are also some properties defined in Crafter CMS that allows us to configure our environment.  Below are the available task properties

+------------------------------------------------------------------------------------------------+
|| Download Properties                                                                           |
+---------------------------+--------------------------------------------------------------------+
|| Property                 || Description                                                       |
+===========================+====================================================================+
|| ``tomcat.version``       || Sets the tomcat version to be downloaded used by                  |
||                          || *downloadTomcat* task                                             |
+---------------------------+--------------------------------------------------------------------+
|| ``groovy.version``       || Sets the groovy version to be downloaded used by                  |
||                          || *downloadGroovy* task                                             |
+---------------------------+--------------------------------------------------------------------+
|| ``solr.version``         || Sets the Solr version to be downloaded used by *downloadSolr* task|
+---------------------------+--------------------------------------------------------------------+
|| ``elasticsearch.version``|| Sets the Elasticsearch version to be downloaded used by           |
||                          || *downloadElasticsearch* task.                                     |
+---------------------------+--------------------------------------------------------------------+
|| ``mariadb4j.version``    || Sets the MariaDb version to be downloaded used by                 |
||                          || *downloadMariaDB4j* task                                          |
+---------------------------+--------------------------------------------------------------------+
|| ``downloadDir``          || Path were all downloads will be saved.                            |
||                          || Default value is *./target/downloads*                             |
+---------------------------+--------------------------------------------------------------------+

+------------------------------------------------------------------------------------------------+
|| Environment Building Properties                                                               |
+-------------------------+----------------------------------------------------------------------+
|| Property               || Description                                                         |
+=========================+======================================================================+
|| ``authoring.root``     || Path were a development environment will be generated.              |
||                        || Default value is *./crafter-authoring/*                             |
+-------------------------+----------------------------------------------------------------------+
|| ``delivery.root``      || Path were a delivery environment will be generated.                 |
||                        || Default value is *./crafter-delivery/*                              |
+-------------------------+----------------------------------------------------------------------+
|| ``crafter.profile``    || Includes Profile in the generation of the development environment.  |
||                        || Default value is false. **If true, MongoDB is required**            |
+-------------------------+----------------------------------------------------------------------+
|| ``crafter.social``     || Includes Social in the generation of the development environment.   |
||                        || Default value is false,                                             |
||                        || **If true, *includeProfile* will be set to true**                   |
+-------------------------+----------------------------------------------------------------------+

.. _authoring-default-ports:

+------------------------------------------------------------------------------------------------+
|| Authoring Environment Properties                                                              |
+-------------------------------------+----------------------------------------------------------+
|| Property                           || Description                                             |
+=====================================+==========================================================+
|| ``authoring.tomcat.http.port``     || Authoring Tomcat Http port. Default value is 8080       |
+-------------------------------------+----------------------------------------------------------+
|| ``authoring.tomcat.shutdown.port`` || Authoring Tomcat shutdown port. Default value is 8005   |
+-------------------------------------+----------------------------------------------------------+
|| ``authoring.tomcat.ajp.port``      || Authoring Tomcat AJP port. Default value is 8009        |
+-------------------------------------+----------------------------------------------------------+
|| ``authoring.tomcat.https.port``    || Authoring Tomcat SSL(https) port. Default value is 8443 |
+-------------------------------------+----------------------------------------------------------+
|| ``authoring.tomcat.debug.port``    || Authoring Tomcat debug port. Default value is 8000      |
+-------------------------------------+----------------------------------------------------------+
|| ``authoring.mongo.port``           || Authoring MongoDb port. Default value is 27020          |
+-------------------------------------+----------------------------------------------------------+
|| ``authoring.elasticsearch.port``   || Authoring Elasticsearch port. Default value is 9201     |
+-------------------------------------+----------------------------------------------------------+
|| ``authoring.solr.port``            || Authoring Solr port. Default value is 8694              |
+-------------------------------------+----------------------------------------------------------+
|| ``authoring.solr.debug.port``      || Authoring Solr debug port. Default value is 5005        |
+-------------------------------------+----------------------------------------------------------+
|| ``authoring.smtp.port``            || Authoring SMTP port. Default value is 25                |
+-------------------------------------+----------------------------------------------------------+
|| ``authoring.mariadb.port``         || Authoring MariaDb port. Default value is 33306          |
+-------------------------------------+----------------------------------------------------------+
|| ``authoring.deployer.port``        || Authoring Deployer port. Default value is 9191          |
+-------------------------------------+----------------------------------------------------------+
|| ``authoring.deployer.debug.port``  || Authoring Deployer debug port. Default value is 5000    |
+-------------------------------------+----------------------------------------------------------+
|| ``authoring.deployment.dir``       || Authoring deployment directory.                         |
||                                    || Default value is "data/repos/sites"                     |
+-------------------------------------+----------------------------------------------------------+

.. _delivery-default-ports:

+------------------------------------------------------------------------------------------------+
|| Delivery Environment Properties                                                               |
+------------------------------------+-----------------------------------------------------------+
|| Property                          || Description                                              |
+====================================+===========================================================+
|| ``delivery.tomcat.http.port``     || Delivery Tomcat Http port. Default value is 9080         |
+------------------------------------+-----------------------------------------------------------+
|| ``delivery.tomcat.shutdown.port`` || Delivery Tomcat Shutdown port. Default value is 9005     |
+------------------------------------+-----------------------------------------------------------+
|| ``delivery.tomcat.ajp.port``      || Delivery Tomcat AJP port. Default value is 9009          |
+------------------------------------+-----------------------------------------------------------+
|| ``delivery.tomcat.https.port``    || Delivery Tomcat SSL(https) port. Default value is 9443   |
+------------------------------------+-----------------------------------------------------------+
|| ``delivery.tomcat.debug.port``    || Delivery Tomcat debug port. Default value is 9000        |
+------------------------------------+-----------------------------------------------------------+
|| ``delivery.mongodb.port``         || Delivery Mongo DB port. Default value is 28020           |
+------------------------------------+-----------------------------------------------------------+
|| ``delivery.elasticsearch.port``   || Delivery Elasticsearch port. Default value is 9202       |
+------------------------------------+-----------------------------------------------------------+
|| ``delivery.solr.port``            || Delivery Solr port. Default value is 8695                |
+------------------------------------+-----------------------------------------------------------+
|| ``delivery.solr.debug.port``      || Delivery Solr debug port. Default value is 5006          |
+------------------------------------+-----------------------------------------------------------+
|| ``delivery.deployer.port``        || Delivery Deployer port. Default value is 9192            |
+------------------------------------+-----------------------------------------------------------+
|| ``delivery.deployer.debug.port``  || Delivery Deployer debug port. Default value is 5001      |
+------------------------------------+-----------------------------------------------------------+
|| ``delivery.deployment.dir``       || Delivery Deployment directory.                           |
||                                   || Default value is "data/repos/sites"                      |
+------------------------------------+-----------------------------------------------------------+
|| ``delivery.smtp.port``            || Delivery SMTP port. Default value is 25                  |
+------------------------------------+-----------------------------------------------------------+

.. _other-properties:

+------------------------------------------------------------------------------------------------+
|| Other Properties                                                                              |
+-------------------------------+----------------------------------------------------------------+
|| Property                     || Description                                                   |
+===============================+================================================================+
|| ``overwriteConfig``          || Overwrite configurations? Default value is false              |
+-------------------------------+----------------------------------------------------------------+
|| ``backupAndReplaceConfig``   || Backup and replace configurations? Default value is false     |
+-------------------------------+----------------------------------------------------------------+
|| ``withSolr``                 || Start Solr ? Default value is false                           |
+-------------------------------+----------------------------------------------------------------+

.. _git-properties:

+------------------------------------------------------------------------------------------------+
|| Git Properties                                                                                |
+-------------------------------+----------------------------------------------------------------+
|| Property                     || Description                                                   |
+===============================+================================================================+
|| ``crafter.git.url``          || Git URL                                                       |
||                              || Default value is "https://github.com/craftercms/"             |
+-------------------------------+----------------------------------------------------------------+
|| ``crafter.git.branch``       || Git source branch. Default value is "master"                  |
+-------------------------------+----------------------------------------------------------------+
|| ``crafter.git.remote``       || Git repository. Default value is "origin"                     |
+-------------------------------+----------------------------------------------------------------+
|| ``crafter.git.shallowClone`` || Perform a shallow clone? Default value is false               |
+-------------------------------+----------------------------------------------------------------+
|| ``crafter.ui.repo``          || Is Studio UI from repository? Default value is false          |
+-------------------------------+----------------------------------------------------------------+

Here's an example using one of the task properties, ``gitRepo``,  to get the latest code from Crafter CMS, in order to have the latest updates from the community:

    .. code-block:: bash

        ./gradlew update -Pcrafter.git.remote=upstream

Here's another example on how to init, build and bundle from a given tag/branch.  Remember to clone the desired branch/tag of craftercms (As described in the next section :ref:`git`),  before running the command below:

    .. code-block:: bash

       ./gradlew init build deploy bundle -Pcrafter.git.branch={BRANCH}/{TAG NAME}

Replace {BRANCH} or {TAG NAME} with the branch and tag you'd like to build.

Here's yet another example of building and deploying the authoring environment of Crafter CMS with Crafter Profile included:

    .. code-block:: bash

       ./gradlew build deploy -Pcrafter.profile=true -Penv=authoring


.. _git:

-------------------
Useful Git Commands
-------------------

Here are some useful Git commands for setting up our Crafter CMS project.

^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Copy Crafter CMS repository and initialize submodules
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

    .. code-block:: bash

       git clone https://github.com/craftercms/craftercms.git
       cd craftercms
       git submodule init

.. _update-submodules:

^^^^^^^^^^^^^^^^^
Update Submodules
^^^^^^^^^^^^^^^^^
1. Run

    .. code-block:: bash

       git submodule update --force --recursive --remote

^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Change Project URL to a fork
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. Change the url on the _.gitmodules_ file
2. Run

    .. code-block:: bash

       git submodule sync --recursive

^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Change the branch/tag of a project (manual way)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. Change the `branch` value in the desire project to valid branch,tag or commit id
2. Run

    .. code-block:: bash

       git submodule sync --recursive

3. Run :ref:`update-submodules`

^^^^^^^^^^^^^^^^^^
Clone a branch/tag
^^^^^^^^^^^^^^^^^^

To clone the branch/tag of craftercms that you want to work with, run:

    .. code-block:: bash

        git clone -b<branch> https://github.com/craftercms/craftercms/

Replace {BRANCH} or {TAG NAME} with the branch and tag you'd like to build.  After cloning the desired branch, you can now init, build and bundle from a given tag/branch using the property `crafter.git.branch` as described in an earlier section :ref:`Git Properties<git-properties>`


