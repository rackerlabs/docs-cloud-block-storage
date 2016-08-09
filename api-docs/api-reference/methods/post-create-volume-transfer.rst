.. _post-create-volume-transfer:

Create a volume transfer
~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    POST /v1/{tenant_id}/os-volume-transfer

This operation creates a volume transfer.

Request parameters
------------------

The request has the following URI parameters.

+--------------------------+-------------------------+------------------------+
|Name                      |Type                     |Description             |
+==========================+=========================+========================+
|{tenant_id}               |String                   |The unique identifier of|
|                          |                         |the tenant or account.  |
+--------------------------+-------------------------+------------------------+

The request has the following body parameters.

+--------------------------+-------------------------+------------------------+
|Name                      |Type                     |Description             |
+==========================+=========================+========================+
|**transfer**              |String *(Required)*      |A representation        |
|                          |                         |of a volume transfer in |
|                          |                         |the creation process.   |
+--------------------------+-------------------------+------------------------+
|transfer.\ **volume_id**  |UUID *(Required)*        |The UUID of the volume. |
+--------------------------+-------------------------+------------------------+
|transfer.\ **name**       |String                   |The volume transfer     |
|                          |                         |name.                   |
+--------------------------+-------------------------+------------------------+

Request example
---------------

The following JSON example creates a volume transfer.

.. code::

   {
        "transfer": {
            "volume_id": "c86b9af4-151d-4ead-b62c-5fb967af0e37",
            "name": "first volume"
        }
   }

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
|transfer.\ **auth_key**   |String                   |The authentication key  |
|                          |                         |for the volume transfer.|
+--------------------------+-------------------------+------------------------+
|transfer.\ **links**      |List                     |The links for the volume|
|                          |                         |transfer.               |
+--------------------------+-------------------------+------------------------+

Response example
----------------

The following example shows the JSON response for creating a volume transfer.

.. code::

   {
       "transfer": {
           "id": "1a7059f5-8ed7-45b7-8d05-2811e5d09f24",
           "created_at": "2015-02-25T03:56:53.081642",
           "name": "first volume",
           "volume_id": "c86b9af4-151d-4ead-b62c-5fb967af0e37",
           "auth_key": "9266c59563c84664",
           "links": [
               {
                   "href": "http://localhost/v2/firstproject/volumes/3",
                   "rel": "self"
               },
               {
                   "href": "http://localhost/firstproject/volumes/3",
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
|202                       |Accepted                 |The request has been    |
|                          |                         |accepted for processing.|
+--------------------------+-------------------------+------------------------+
