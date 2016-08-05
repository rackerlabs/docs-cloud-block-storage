.. _get-volume—transfer-detail:

Retrieve a volume transfer (detailed)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    GET /v1/{tenant_id}/os-volume-transfer/​{transfer_id}​

This operation retrieves details for a volume transfer specified by
``transfer_id``.

Request
-------

The request has the following URI parameters.

+--------------------------+-------------------------+------------------------+
|Name                      |Type                     |Description             |
+==========================+=========================+========================+
|{tenant_id}               |String                   |The unique identifier of|
|                          |                         |the tenant or account.  |
+--------------------------+-------------------------+------------------------+
|{transfer_id}             |String                   |The unique identifier   |
|                          |                         |for a volume transfer.  |
+--------------------------+-------------------------+------------------------+

This operation does not accept a request body.

Response parameters
-------------------

The response has the following body parameters.

+--------------------------+-------------------------+------------------------+
|Name                      |Type                     |Description             |
+==========================+=========================+========================+
|**transfer**              |String                   |A representation        |
|                          |                         |of a volume transfer in |
|                          |                         |the creation process.   |
+--------------------------+-------------------------+------------------------+
|transfer.\ **id**         |UUID                     |The UUID of the volume  |
|                          |                         |transfer.               |
+--------------------------+-------------------------+------------------------+
|transfer.\ **created_at** |Datetime                 |The date and time when  |
|                          |                         |the volume was created. |
+--------------------------+-------------------------+------------------------+
|transfer.\ **name**       |String                   |The volume transfer     |
|                          |                         |name.                   |
+--------------------------+-------------------------+------------------------+
|transfer.\ **volume_id**  |UUID                     |The UUID of the volume. |
+--------------------------+-------------------------+------------------------+
|transfer.\ **links**      |List                     |The links for the volume|
|                          |                         |transfer.               |
+--------------------------+-------------------------+------------------------+

Response example
----------------

The following example shows the JSON response for retrieving details for a
specified volume transfer.

.. code::

   {
       "transfer": {
           "id": "cac5c677-73a9-4288-bb9c-b2ebfb547377",
           "created_at": "2015-02-25T03:56:53.081642",
           "name": "first volume transfer",
           "volume_id": "894623a6-e901-4312-aa06-4275e6321cce",
           "links": [
               {
                   "href": "http://localhost/v2/firstproject/volumes/1",
                   "rel": "self"
               },
               {
                   "href": "http://localhost/firstproject/volumes/1",
                   "rel": "bookmark"
               }
           ]
       }
   }

Response codes
--------------

This operation can have the following response codes.

+--------------------------+-------------------------+------------------------+
|Response Code             |Name                     |Description             |
+==========================+=========================+========================+
|200                       |OK                       |Success                 |
+--------------------------+-------------------------+------------------------+
