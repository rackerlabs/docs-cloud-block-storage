.. _snapshots-operations:

=========
Snapshots
=========

.. contents::
   :depth: 1
   :local:

A snapshot is a point-in-time copy of the data that a volume contains.

When you make an API call to create, list, or delete snapshots, the following
status values are possible:

* CREATING: The snapshot is being created.

* AVAILABLE: The snapshot is ready for use.

* DELETING: The snapshot is being deleted.

* ERROR: An error occurred during snapshot creation.

* ERROR_DELETING: An error occurred during snapshot deletion.

.. include:: methods/post-create-snapshot-v1-tenant-id-snapshots.rst
.. include:: methods/get-list-snapshots-v1-tenant-id-snapshots.rst
.. include:: methods/get-list-snapshots-(detailed)-v1-tenant-id-snapshots-detail.rst
.. include:: methods/get-show-snapshot-details-v1-tenant-id-snapshots-snapshot-id.rst
.. include:: methods/put-update-snapshot-v1-tenant-id-snapshots-snapshot-id.rst
.. include:: methods/delete-delete-snapshot-v1-tenant-id-snapshots-snapshot-id.rst
.. include:: methods/get-show-snapshot-metadata-v1-tenant-id-snapshots-snapshot-id-metadata.rst
