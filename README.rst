.. image:: https://travis-ci.org/martinhoefling/rsyncd-formula.svg?branch=master
    :target: https://travis-ci.org/martinhoefling/rsyncd-formula

================
rsyncd-formula
================

A formula to install and configure rsync as daemon process.

.. note::

    See the full `Salt Formulas installation and usage instructions
    <http://docs.saltstack.com/en/latest/topics/development/conventions/formulas.html>`_.

Available states
================

.. contents::
    :local:

``rsyncd``
------------

Installs the rsync package, and starts the rsyncd service. Note: The rsyncd.conf has to be created manually / via another state. If the state of the config should also be managed via salt, the rsyncd.config state (which pulls rsyncd) should be used instead.

``rsyncd.config``
------------

Configure the rsync daemon by writing an rsync.conf and rsync secrets (optional).

Testing
=======

This command will apply the `rsyncd` state on localhost with the example pillar. Perfect for testing in containers::

    salt-call state.sls rsyncd --local --retcode-passthrough --file-root=$(pwd) --pillar-root=test/pillar
