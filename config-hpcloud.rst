Configuring for HPCloud
=======================

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

The essential configuration sections for HPCloud look like this:


::

    
      hpcloud:
        type: openstack
        use-floating-ip: false
        admin-secret: 139e8bee94d15bff96d91ab9c27e5efc
        # Globally unique swift bucket name
        control-bucket: juju-9b53d6f5f45968d7c392a221f85fc8ae
        auth-url: https://region-a.geo-1.identity.hpcloudsvc.com:35357/v2.0/
        public-bucket-url: https://region-a.geo-1.objects.hpcloudsvc.com/v1/60502529753910
        auth-mode: userpass
        username: [your username]
        password: [password]
        tenant-name: [HP Cloud Project Name]
        region: [az-1.region-a.geo-1, az-2.region-a.geo-1, or az-3.region-a.geo-1]


The items highlighted are values you will need to enter, and are
explained below. You will find most of the relevant information on the
`HP Cloud API Keys page`_


+ ``tenant-name:`` For HPCloud, this is listed as the project name on
  the `"Manage Projects" page`_.

  .. image:: _img/getting_started-hpc-tenant.png

You will find the following information on the `HP Cloud API Keys
page for your account`_.

+ ``auth-url:`` This is the keystone url for authentication. It is given
  (on a region by region basis) under the heading "Service Endpoints -
  identity"

  .. image:: _img/getting_started-hpc-config1.png

+ ``region:`` This is the longer format region name, given under the
  headings for Block Storage and Compute sections.

  .. image:: _img/getting_started-hpc-region.png

+ ``username:`` Enter your HP Cloud login username.
+ ``password:`` Enter your HP Cloud login password.
+ ``public-bucket-url:`` Currently up to date tools are provided to HP
  Cloud by a public bucket. If you're using your own imagemetadata you'd
  change this URL to the bucket you've created.

.. _Canonical Ltd: http://canonical.com
.. _Juju Labs: https://juju.ubuntu.com/labs/
.. _The charm store: https://juju.ubuntu.com/docs/authors-charm-store.html
.. _Try Juju: https://jujucharms.com/sidebar/
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
.. _ HP Cloud API Keys page for your account.: https://account.hpcloud.com/account/api_keys
.. _ "Manage Projects" page: https://account.hpcloud.com/projects
.. _Events: https://juju.ubuntu.com/events/
.. _Write a charm: https://juju.ubuntu.com/docs/authors-charm-writing.html
.. _File a bug: https://bugs.launchpad.net/juju-website/+filebug
.. _Documentation: index
.. _Charm store: https://jujucharms.com/
.. _Juju Blog: https://juju.ubuntu.com/community/blog/
.. _Tutorial: index#test
.. _Charmers: https://juju.ubuntu.com/community/charmers/
.. _Resources: https://juju.ubuntu.com/resources/
.. _Features: https://juju.ubuntu.com/features/
.. _Deploy: https://juju.ubuntu.com/deployment/
.. _Videos: https://juju.ubuntu.com/resources/videos/


