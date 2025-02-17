Node Clone
---------------------

The Clone module allows users to make a copy of an existing node and then edit
that copy easily.  This module has also been used by some to facilitate node templating.

Installation
------------

Install this module using the official Backdrop CMS instructions at https://backdropcms.org/guide/modules

Setup your options at: /admin/config/content/clone

Usage
-----

The clone module allows users to make a copy of an existing node and then edit
that copy. The authorship is set to the current user, the menu and url aliases
are reset, and the (localized) words "Clone of" are inserted into the title to
remind you that you are not editing the original node.

Users with the "clone node" or "clone own nodes" permission can utilize this
functionality. A "Clone content" local action link will appear on node pages.
Depending on the setting you choose there are two possible actions that will
occur when you click that tab. Each of these is a different cloning "method".

The default method works by pre-populating the node form, rather than immediately
saving a copy of the original node to the database.  Thus, your node will not
be saved until you hit "Submit" (just like if you went to node/add/x).

The alternative method that may be selected immediately saves the node (by
default the user must confirm this action on a confirmation form). This may
work better in some cases, but also means that the copied node may immediately
show up on the front page or in RSS feeds even while you are editing it.

This module makes reasonable checks on access permissions.  A user cannot clone
a node unless they can use the input format of that node, and unless they have
permission to create new nodes of that type based on a call to node_access().

Settings can be accessed at admin/config/content/clone.  On this page you can
set whether the publishing options are reset when making a clone of a node.
This is set for each node type individually.

This module seems to work with common node types, however YMMV (your mileage may vary),
especially with nodes that have any sort of image or file  attachments.  In all cases,
but especially if you are using a complex (non-core) field or custom node type,
you should evaluate this module on a test site with a copy of your database
before attempting to use it on a live site. On the settings page you may choose
node types to be omitted from the cloning mechanism - no users will be able
to clone a node of an omitted type. For example, if you use Field Collections,
you may need to also enable the extra Field Collection Node Clone module from
https://www.drupal.org/project/field_collection_node_clone Otherwise, the cloned
node will reference the items in the original field collection.

This module makes no attempt to respect field-level permissions set via
the Field Permissions module, or any other module that implements
field-level permissions hooks. You should test your configuration
carefully or not allow access to the clone functionality for non-admins if
you rely on field-level permissions for important site features.

Note: this module originally derived from code posted by Steve Ringwood
(nevets@drupal) at http://drupal.org/node/73381#comment-137714

License
-------

This project is GPL v2 software. See the LICENSE.txt file in this directory for complete text.

Credits
-------

[Peter Wolanin](https://www.drupal.org/u/pwolanin)

Maintainers
-----------

- [Robert Garrigós](https://github.com/robertgarrigos)
- seeking

Ported to Backdrop by:

- [biolithic](https://github.com/biolithic)
