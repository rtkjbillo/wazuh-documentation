.. _installation_guide:

Installation guide
==================

This document will guide you through the Wazuh installation process. For interactive help, our `email forum <https://groups.google.com/d/forum/wazuh>`_ is available. You can subscribe to this forum by sending an email to `Wazuh subscribe <mailto:wazuh%2Bsubscribe@googlegroups.com>`_.

Setting up Wazuh involves the installation of two central components: the Wazuh server and Elastic Stack. In addition, Wazuh agents are deployed to the monitored hosts in your environment:

- **Wazuh server:** Runs the Wazuh manager, API and Filebeat (Filebeat is only necessary in **distributed architecture**). It collects and analyzes data from deployed agents.

+ **Elastic Stack**: Runs the Elasticsearch engine, Logstash server and Kibana (including the Wazuh App). It reads, parses, indexes, and stores alert data generated by the Wazuh server.

- **Wazuh agent**: Runs on the monitored host, collecting system log and configuration data and detecting intrusions and anomalies. It talks with the Wazuh server to which it forwards collected data for further analysis.

**Distributed architectures** run the Wazuh server and Elastic Stack cluster (one or more servers) on different hosts. **Single-host architectures** run the Wazuh server and Elastic Stack on the same system. This guide covers both installation options.

The diagrams below list the components that are run per host for single-host and distributed architectures.

**Single-host architecture**:

.. thumbnail:: ../images/installation/installing_wazuh_singlehost.png
    :title: Installing Wazuh server - single server architecture
    :align: center
    :width: 100%

**Distributed architecture**:

.. thumbnail:: ../images/installation/installing_wazuh.png
    :title: Installing Wazuh server - distributed architecture
    :align: center
    :width: 100%

.. note::
  Before installing the components, please confirm that the time synchronization service is configured and working on your servers. This is most commonly done with **NTP**.  For more information, go to `Debian/Ubuntu <https://help.ubuntu.com/lts/serverguide/NTP.html>`_ or `CentOS/RHEL/Fedora <http://www.tecmint.com/install-ntp-server-in-centos/>`_.

.. topic:: Contents

    .. toctree::
        :maxdepth: 2

        installing-wazuh-server/index
        installing-elastic-stack/index
        installing-wazuh-agent/index
        optional-configurations/index
        upgrading/index
        virtual-machine
      	packages-list/index
        compatibility_matrix/index
