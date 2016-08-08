.. _get-volume—transfers-detailed:

Retrieve the volume transfers (detailed)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    GET /v1/{tenant_id}/os-volume-transfer/detail

This operation retrieves detailed information for the volume transfers for the
specified ``tenant_id``.

Request
-------

The request has the following URI parameters.

+--------------------------+-------------------------+------------------------+
|Name                      |Type                     |Description             |
+==========================+=========================+========================+
|{tenant_id}               |String                   |The unique identifier of|
|                          |                         |the tenant or account.  |
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

The following example shows the JSON response for retrieving  detailed
information for the volume transfers for a specified ``tenant_id``.

.. code::

   {
       "transfers": [
           {
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
           },
           {
               "id": "f26c0dee-d20d-4e80-8dee-a8d91b9742a1",
               "created_at": "2015-03-25T03:56:53.081642",
               "name": "second volume transfer",
               "volume_id": "673db275-379f-41af-8371-e1652132b4c1",
               "links": [
                   {
                       "href": "http://localhost/v2/firstproject/volumes/2",
                    "rel": "self"
                   },
                   {
                       "href": "http://localhost/firstproject/volumes/2",
                    "rel": "bookmark"
                   }
               ]
           }
       ]
   }

Response codes
--------------

This operation can have the following response codes.

+--------------------------+-------------------------+------------------------+
|Response Code             |Name                     |Description             |
+==========================+=========================+========================+
|200                       |OK                       |Success                 |
+--------------------------+-------------------------+------------------------+
