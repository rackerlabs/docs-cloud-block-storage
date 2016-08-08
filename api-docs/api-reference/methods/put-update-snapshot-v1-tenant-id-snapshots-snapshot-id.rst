.. _put-update-snapshot:

Update a snapshot
~~~~~~~~~~~~~~~~~

.. code::

    PUT /v1/{tenant_id}/snapshots/{snapshot_id}

This operation updates a specified snapshot.

Request parameters
------------------

The request has the following URI parameters.

+--------------------------+-------------------------+------------------------+
|Name                      |Type                     |Description             |
+==========================+=========================+========================+
|{tenant_id}               |String                   |The unique identifier of|
|                          |                         |the tenant or account.  |
+--------------------------+-------------------------+------------------------+
|{snapshot_id}             |String                   |The unique identifier of|
|                          |                         |an existing snapshot.   |
+--------------------------+-------------------------+------------------------+

The request has the following body parameters.

+--------------------------+-------------------------+------------------------+
|Name                      |Type                     |Description             |
+==========================+=========================+========================+
|**snapshot**              |String *(Required)*      |Information about the   |
|                          |                         |snapshot.               |
+--------------------------+-------------------------+------------------------+
|snapshot.\                |String                   |A description of the    |
|**display_description**   |                         |snapshot.               |
+--------------------------+-------------------------+------------------------+
|snapshot.\                |String                   |The name of the         |
|**display_name**          |                         |snapshot.               |
+--------------------------+-------------------------+------------------------+


Request examples
----------------

The following XML example updates a snapshot.

.. code::

   <?xml version="1.0" encoding="UTF-8"?>
   <snapshot xmlns="http://docs.rackspace.com/volume/api/v1"
             display_name="snap-001"
             display_description="This is yet, another snapshot."/>

The following JSON example updates a snapshot.

.. code::

   {
       "snapshot":{
           "display_name":"snap-001",
           "display_description":"This is yet, another snapshot."
       }
   }

Response examples
-----------------

The following example shows the XML response for updating a snapshot.

.. code::

   <?xml version='1.0' encoding='UTF-8'?>
   <snapshot
       xmlns:os-extended-snapshot-attributes="http://docs.rackspace.com/volume/api/v1"
       status="available"
       display_description="This is yet, another snapshot"
       created_at="2013-02-20T08:11:34.000000"
       volume_id="2402b902-0b7a-458c-9c07-7435a826f794"
       size="1"
       id="4b502fcb-1f26-45f8-9fe5-3b9a0a52eaf2"
       display_name="vol-001"
       os-extended-snapshot-attributes:project_id="0c2eba2c5af04d3f9e9d0d410b371fde"
       os-extended-snapshot-attributes:progress="100%">
       <metadata/>
   </snapshot>

The following example shows the JSON response for updating a snapshot.

.. code::

   {
       "snapshot":{
           "created_at":"2013-02-20T08:11:34.000000",
           "display_description":"This is yet, another snapshot",
           "display_name":"vol-001",
           "id":"4b502fcb-1f26-45f8-9fe5-3b9a0a52eaf2",
           "size":1,
           "status":"available",
           "volume_id":"2402b902-0b7a-458c-9c07-7435a826f794"
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
