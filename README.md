# Overview

This charm provides gitlab from http://gitlab.org. Gitlab is a self hosted git management software based on gitolite and rails. It provides a neat source code repository management interface in the likes of github.

# Installation

To install this charm, first edit config.yaml to suite your needs and schedule the following juju actions:

    juju deploy postgresql
    juju deploy gitlab

Set the default admin password:

  juju set gitlab admin_password=<password>

You can then add a relation between gitlab and mysql with:

    juju add-relation gitlab:db postgresql

Finally you need to expose your gitlab instance:

    juju expose gitlab


# Configuration

admin_password sets the admin password for the gitlab unit

# How to access GitLab

To access your freshly installed GitLab charm instance you need to go to the public address of you gitlab unit and provide the admin user name and password.

The default admin username is admin@local.host and the password should be the one set at config.yaml admin_password configuration option.

# Contact Information

Author: Helio L Mota
Report bugs at: http://bugs.launchpad.net/charms/+source/gitlab
Location: http://jujucharms.com/charms/precise/gitlab

# TODO
Figure out if we actually need to install go/gitlab-git-http-server. Instructions are unclear, and we're using nginx to serve the site.
