.. _snapshots-operations-v2:

Snapshots
~~~~~~~~~


A snapshot is a point-in-time copy of the data that a volume contains.

When you create, list, update, or delete volumes, the following status values are possible:

* CREATING: The snapshot is being created.

* AVAILABLE: The snapshot is ready for use.

* DELETING: The snapshot is being deleted.

* ERROR: An error occurred during snapshot creation.

* ERROR_DELETING: An error occurred during snapshot deletion.


.. include:: methods-v2/post-create-snapshot-v2.rst
.. include:: methods-v2/get-list-snapshots-v2.rst
.. include:: methods-v2/get-list-snapshots-(detailed)-v2.rst
.. include:: methods-v2/get-show-snapshot-details-v2.rst
.. include:: methods-v2/put-update-snapshot-v2.rst
.. include:: methods-v2/delete-snapshot-v2.rst
.. include:: methods-v2/get-show-snapshot-metadata-v2.rst