Configuring for MAAS
====================

Metal As A Service is software which allows you to deal with physical
hardware just as easily as virtual nodes. For more information about
MAAS, see `maas.ubuntu.com`_

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

Get your API key
----------------

You'll need an API key from MAAS so that the Juju client can access
it. Each user account in MAAS can have as many API keys as desired.
One hard and fast rule is that you'll need to use a different API key
for each Juju environment you set up within a single MAAS cluster.

To get the API key:


#. Go to your MAAS preferences page, or go to your MAAS home page and
   choose Preferences from the drop-down menu that appears when clicking
   your username at the top-right of the page.
#. Optionally add a new MAAS key. Do this if you're setting up another
   environment within the same MAAS cluster.
#. Copy the key value - you will need it shortly!

Edit or create the configuration
--------------------------------

Create or modify ``~/.juju/environments.yaml`` with the following
content:

::

    
      maas:
        type: maas
        maas-server: 'http://xxyourMAASServernamexx:80/MAAS'
        maas-oauth: '$MAAS_API_KEY'
        admin-secret: 'nothing'
        default-series: 'precise'


Substitute the API key from earlier into the ``$MAAS_API_KEY`` slot. You
may need to modify the ``maas-server`` setting too; if you're running
from the maas package it should be something like
"http://hostname.xxxx.yyy/MAAS".

.. _Canonical Ltd: http://canonical.com
.. _Juju Labs: https://juju.ubuntu.com/labs/
.. _The charm store: https://juju.ubuntu.com/docs/authors-charm-store.html
.. _Overview: https://juju.ubuntu.com/resources/juju-overview/
.. _Resources: https://juju.ubuntu.com/resources
.. _Community: https://juju.ubuntu.com/community/
.. _Download Juju: https://juju.ubuntu.com/download/
.. _maas.ubuntu.com: http://maas.ubuntu.com
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
.. _Tutorial: getting-started.html#test
.. _Charmers: https://juju.ubuntu.com/community/charmers/
.. _Resources: https://juju.ubuntu.com/resources/
.. _Features: https://juju.ubuntu.com/features/
.. _Deploy: https://juju.ubuntu.com/deployment/
.. _Videos: https://juju.ubuntu.com/resources/videos/


