Configuring for OpenStack
=========================

You should start by generating a generic configuration file for Juju,
using the command:

::

    juju generate-config


This will generate a file, environments.yaml , which will live in your
~/.juju/ directory (and will create the directory if it doesn't
already exist).

.. note:: If you have an existing configuration, you can use ``juju
   generate-config --show`` to output the new config file, then copy and
   paste relevant areas in a text editor etc.

The essential configuration sections for OpenStack look like this:


::

    
    openstack:
      type: openstack
      # Specifies whether the use of a floating IP address is required to give the nodes
      # a public IP address. Some installations assign public IP addresses by default without
      # requiring a floating IP address.
      # use-floating-ip: false
      admin-secret: 13850d1b9786065cadd0f477e8c97cd3
      # Globally unique swift bucket name
      control-bucket: juju-fd6ab8d02393af742bfbe8b9629707ee
      # Usually set via the env variable OS_AUTH_URL, but can be specified here
      # auth-url: https://yourkeystoneurl:443/v2.0/
      # override if your workstation is running a different series to which you are deploying
      # default-series: precise
      # The following are used for userpass authentication (the default)
      auth-mode: userpass
      # Usually set via the env variable OS_USERNAME, but can be specified here
      # username: 
      # Usually set via the env variable OS_PASSWORD, but can be specified here
      # password: 
      # Usually set via the env variable OS_TENANT_NAME, but can be specified here
      # tenant-name: 
      # Usually set via the env variable OS_REGION_NAME, but can be specified here
      # region: 


.. note:: At any time you can run ``juju init --show`` to display the most
   revent version of the environments.yaml template file, instead of
   having it write to file.

Remember to substitute in the parts of the snippet that are important
to you. If you are deploying on OpenStack the following documentation
might also be useful:

`Ubuntu Cloud Infrastructure`_

.. _Canonical Ltd: http://canonical.com
.. _Juju Labs: https://juju.ubuntu.com/labs/
.. _The charm store: https://juju.ubuntu.com/docs/authors-charm-store.html
.. _Overview: https://juju.ubuntu.com/resources/juju-overview/
.. _Resources: https://juju.ubuntu.com/resources
.. _Community: https://juju.ubuntu.com/community/
.. _Download Juju: https://juju.ubuntu.com/download/
.. _Weekly charm meeting: https://juju.ubuntu.com/community/weekly-charm-meeting/
.. _Features: https://juju.ubuntu.com/features
.. _The Juju web UI: https://juju.ubuntu.com/resources/the-juju-gui/
.. _Deployment: https://juju.ubuntu.com/deployment
.. _Help with documentation: https://juju.ubuntu.com/docs/contributing.html
.. _Community: https://juju.ubuntu.com/community
.. _Charms: https://juju.ubuntu.com/charms
.. _Charms: https://juju.ubuntu.com/charms/
.. _Easy tasks for new developers: https://juju.ubuntu.com/resources/easy-tasks-for-new-developers/
.. _Juju: https://juju.ubuntu.com/
.. _Try Juju: https://jujucharms.com/sidebar/
.. _Events: https://juju.ubuntu.com/events/
.. _Write a charm: https://juju.ubuntu.com/docs/authors-charm-writing.html
.. _File a bug: https://bugs.launchpad.net/juju-website/+filebug
.. _Ubuntu Cloud Infrastructure: https://help.ubuntu.com/community/UbuntuCloudInfrastructure
.. _Documentation: https://juju.ubuntu.com/docs/
.. _Charm store: https://jujucharms.com/
.. _Juju Blog: https://juju.ubuntu.com/community/blog/
.. _Tutorial: getting-started#test
.. _Charmers: https://juju.ubuntu.com/community/charmers/
.. _Resources: https://juju.ubuntu.com/resources/
.. _Features: https://juju.ubuntu.com/features/
.. _Deploy: https://juju.ubuntu.com/deployment/
.. _Videos: https://juju.ubuntu.com/resources/videos/


