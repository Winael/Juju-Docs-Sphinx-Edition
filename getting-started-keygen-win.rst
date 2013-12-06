Creating SSH Keypairs on Windows
================================

This walkthrough will show you how to create SSH keys for use with
Juju on the Windows OS.

1. Create the .ssh folder
-------------------------

First you need to create a folder called .ssh in your Home directory,
which is where ssh keys will be kept.

One way to do this is to open the Start Menu and type "cmd" (without
quotes) in the search box at the bottom of the Start Menu. Click on
cmd.exe when it comes up in the search results. This will open up a
Windows command prompt.

Type the following in the command prompt:

::

    mkdir .ssh


This will create a folder called .ssh in your home directory.

2. Download puttygen.exe
------------------------

Download puttygen.exe from the `PuTTY download page`_
The file you download is not an installer, but a simple executable you
can run directly.

Once downloaded, run puttygen.exe, you should see a dialog that looks
like this:


3. Generating your keys
-----------------------

The defaults for the parameters at the bottom of the window are
correct (SSH-2 RSA and 2048 bits). Click generate, and move your mouse
back and forth over the window to generate your key.

It is recommended that you specify a passphrase (password) for your
key, so that if it is lost, it can't be used without the password.
Choose a password you can remember, because it cannot be recovered if
forgotten.

4. Save your keys
-----------------

Click Conversions->Export OpenSSH Key on the main menu. Find the .ssh
folder you created earlier and save the key in that folder with the
name id_rsa (no extension). This is where Juju and some other programs
will look for it by default.

Next, you need to save your public key. To do this, right click in the
box under "Public key for pasting into OpenSSH authorized_keys file",
and click "Select All". Copy the text using Ctrl-C or right-click
Copy.

Open Notepad and paste the contents of the clipboard. Save the file
with the name id_rsa.pub in the same directory where you saved the
private key (note, the extension should be .pub, not .txt).

That's it! You now have ssh keys that can be used with Juju and other
applications that require ssh keys.

.. _Canonical Ltd: http://canonical.com
.. _Juju Labs: https://juju.ubuntu.com/labs/
.. _The charm store: https://juju.ubuntu.com/docs/authors-charm-store.html
.. _Overview: https://juju.ubuntu.com/resources/juju-overview/
.. _Resources: https://juju.ubuntu.com/resources
.. _Community: https://juju.ubuntu.com/community/
.. _PuTTY download page: http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html
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
.. _Documentation: https://juju.ubuntu.com/docs/
.. _Charm store: https://jujucharms.com/
.. _Juju Blog: https://juju.ubuntu.com/community/blog/
.. _Tutorial: https://juju.ubuntu.com/docs/getting-started.html#test
.. _Charmers: https://juju.ubuntu.com/community/charmers/
.. _Resources: https://juju.ubuntu.com/resources/
.. _Features: https://juju.ubuntu.com/features/
.. _Deploy: https://juju.ubuntu.com/deployment/
.. _Videos: https://juju.ubuntu.com/resources/videos/


