Configuring for Windows Azure
=============================

This process requires you to have an Windows Azure account. If you
have not signed up for one yet, it can obtained at
`http://www.windowsazure.com/`_.

You should start by generating a generic configuration file for Juju,
using the command:

::

    juju generate-config


This will generate a file, environments.yaml , which will live in your
~/.juju/ directory (and will create the directory if it doesn't
already exist).

.. note:: The above command will not overwrite your existing
   environments.yaml file, or output to stdout. In order to see the
   boilerplate environment.yaml on stdout you need to append the ``--show``
   option. This is helpful if you have an existing environment.yaml and
   just need to add a section. For example:


::

    juju generate-config --show


You can then copy and paste the needed section.

The generic configuration sections generated for Windows Azure will
look something like this:


::

    
      azure:
        type: azure
        admin-secret: 35d65be36c72da940933dd02f8d7cef0
        # Location for instances, e.g. West US, North Europe.
        location: West US
        # http://msdn.microsoft.com/en-us/library/windowsazure
        # Windows Azure Management info.
        management-subscription-id: 886413e1-3b8a-5382-9b90-0c9aee199e5d
        management-certificate-path: /home/me/azure.pem
        # Windows Azure Storage info.
        storage-account-name: juju0useast0
        # Public Storage info (account name and container name) denoting a public
        # container holding the juju tools.
        # public-storage-account-name: jujutools
        # public-storage-container-name: juju-tools
        # Override OS image selection with a fixed image for all deployments.
        # Most useful for developers.
        # force-image-name: b39f27a8b8c64d52b05eac6a62ebad85__Ubuntu-13_10-amd64-server-DEVELOPMENT-20130713-Juju_ALPHA-en-us-30GB
        # Pick a simplestreams stream to select OS images from: daily or released
        # images, or any other stream available on simplestreams.  Leave blank for
        # released images.
        # image-stream: ""
        # default-series: precise
                


This is the configuration environments.yaml file needed to run on
Windows Azure. You will need to set the ``management-subscription-id``,
``management-certificate-path``, and ``storage-account-name``.

.. note:: Other than ``location`` the other key vaule defaults are
   recommended, but can be updated to your preference.

Config Values
-------------

Generate a new certificate for juju usage (or use an existing one).
Suggest to use a 'Common Name' with 'Juju' in it so its obvious in the
web UI later. Run the following commands on Ubuntu to generate a new
certificate:

::

    
    openssl req -x509 -nodes -days 3650 -newkey rsa:2048 -keyout azure.pem -out azure.pem
    openssl x509 -inform pem -in azure.pem -outform der -out azure.cer
    chmod 600 azure.pem
                


Login to the Windows Azure console @ `https://manage.windowsazure.com`_. From here you can gather the
following information:


+ Settings Left Navigation: get the ``SUBSCRIPTION ID`` of the account
  you upload to. This will be used for the ``management-subscription-id``
+ Settings Left Navigation: "upload" the MyCert.cer file above (if you
  created one). This is the certificate you used for the ``management-
  certificate-path``
+ Storage Left Navigation:

    + Click New (bottom left)
    + Click Quick Create
    + Add a name in url (for example ``juju0useast0``). This is the value to
      be used for ``storage-account-name``.
    + Select Location (for example: East US)
    + Select Subscription
    + Disable "Enable Geo-Replication" (not applicable)

.. topic:: Note:

   You must create the storage account in the same region/location
   specified by the ``location`` key value. For example, if ``location: West
   US`` is set then ``storage-account-name:`` must also have a storage set
   up in ``West US``. Failure to do so will result in a group affinity
   error.

Ensure the environments.yaml is configured with the above values and
save.

.. _Canonical Ltd: http://canonical.com
.. _Juju Labs: https://juju.ubuntu.com/labs/
.. _The charm store: https://juju.ubuntu.com/docs/authors-charm-store.html
.. _Overview: https://juju.ubuntu.com/resources/juju-overview/
.. _Resources: https://juju.ubuntu.com/resources
.. _https://manage.windowsazure.com: https://manage.windowsazure.com
.. _Community: https://juju.ubuntu.com/community/
.. _Download Juju: https://juju.ubuntu.com/download/
.. _http://www.windowsazure.com/: http://www.windowsazure.com/
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
.. _Documentation: index.html
.. _Charm store: https://jujucharms.com/
.. _Juju Blog: https://juju.ubuntu.com/community/blog/
.. _Tutorial: index.html#test
.. _Charmers: https://juju.ubuntu.com/community/charmers/
.. _Resources: https://juju.ubuntu.com/resources/
.. _Features: https://juju.ubuntu.com/features/
.. _Deploy: https://juju.ubuntu.com/deployment/
.. _Videos: https://juju.ubuntu.com/resources/videos/


