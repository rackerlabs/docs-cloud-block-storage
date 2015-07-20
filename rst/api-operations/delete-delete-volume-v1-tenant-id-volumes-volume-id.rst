
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

=============================================================================
Delete Volume -  Rackspace Cloud Block Storage Developer Guide
=============================================================================

Delete Volume
~~~~~~~~~~~~~~~~~~~~~~~~~

`Request <delete-delete-volume-v1-tenant-id-volumes-volume-id.html#request>`__
`Response <delete-delete-volume-v1-tenant-id-volumes-volume-id.html#response>`__

.. code::

    DELETE /v1/{tenant_id}/volumes/{volume_id}

Deletes a volume.

.. note::
   If a snapshot of the volume exists, you cannot delete the volume until you delete the snapshot.
   
   



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|202                       |                         |                         |
+--------------------------+-------------------------+-------------------------+


Request
^^^^^^^^^^^^^^^^^

This table shows the URI parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|{tenant_id}               |xsd:string               |The unique identifier of |
|                          |                         |the tenant or account.   |
+--------------------------+-------------------------+-------------------------+
|{volume_id}               |*(Required)*             |The unique identifier of |
|                          |                         |an existing volume.      |
+--------------------------+-------------------------+-------------------------+








Response
^^^^^^^^^^^^^^^^^^




