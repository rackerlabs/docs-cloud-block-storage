
.. _delete-volume-v2:

Delete volume
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    DELETE /v2/{tenant_id}/volumes/{volume_id}

This operation deletes a volume.

.. note::
   If a snapshot of the volume exists, you cannot delete the volume until you delete the snapshot.



**Preconditions**

-   Volume status must be ``available``, ``in-use``, ``error``, or ``error_restoring``.

-   You cannot already have a snapshot of the volume.

-   You cannot delete a volume that is in a migration.

**Asynchronous postconditions**

-   The volume is deleted in volume index.

-   The volume managed by Cloud Block Storage is deleted in storage node.

**Troubleshooting**

-   If volume status remains in ``deleting`` or becomes ``error_deleting`` the request failed. Ensure you meet the preconditions then investigate the storage back end.

-   The volume managed by OpenStack Block Storage is not deleted from the storage system.

   
   



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|202                       |Accepted                 |The request has been     |
|                          |                         |accepted for processing. |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""




This table shows the URI parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|{tenant_id}               |UUID *(Required)*        |The UUID of the tenant in|
|                          |                         |a multi-tenancy cloud.   |
+--------------------------+-------------------------+-------------------------+
|{volume_id}               |UUID *(Required)*        |The UUID of              |
|                          |                         |an existing volume.      |
+--------------------------+-------------------------+-------------------------+





This operation does not accept a request body.




Response
""""""""""""""""






This operation does not return a response body.




