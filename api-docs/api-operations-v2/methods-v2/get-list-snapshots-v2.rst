
.. _get-list-snapshots-v2:

List snapshots
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /v2/{tenant_id}/snapshots

This operation lists summary information for all Cloud Block Storage snapshots that the tenant who submits the request can access.



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |OK                       |Success                  |
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


This table shows the query parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|sort_key                  |String *(Optional)*      |Sorts by an attribute. A |
|                          |                         |valid value is ``name``, |
|                          |                         |``status``, ``container-f|
|                          |                         |ormat``, ``disk-format``,|
|                          |                         |``size``, ``id``,        |
|                          |                         |``created-at``, or       |
|                          |                         |``updated-at``.          |
|                          |                         |Default is               |
|                          |                         |``created-at``.          |
|                          |                         |The API uses the         |
|                          |                         |natural sorting direction|
|                          |                         |of the ``sort-key``      |
|                          |                         |attribute value.         |
+--------------------------+-------------------------+-------------------------+
|sort_dir                  |String *(Optional)*      |Sorts by one or more sets|
|                          |                         |of attribute and sort    |
|                          |                         |direction combinations.  |
|                          |                         |If you omit the sort     |
|                          |                         |direction in a set,      |
|                          |                         |default is ``desc``      |
|                          |                         |(descending).            |
+--------------------------+-------------------------+-------------------------+
|limit                     |Integer *(Optional)*     |Requests a page size of  |
|                          |                         |items. Returns a number  |
|                          |                         |of items up to a limit   |
|                          |                         |value. Use the ``limit`` |
|                          |                         |parameter to make an     |
|                          |                         |initial limited request  |
|                          |                         |and use the ID of the    |
|                          |                         |last-seen item from the  |
|                          |                         |response as the          |
|                          |                         |``marker`` parameter     |
|                          |                         |value in a subsequent    |
|                          |                         |limited request.         |
+--------------------------+-------------------------+-------------------------+
|marker                    |String *(Optional)*      |The ID of the last-seen  |
|                          |                         |item. Use the ``limit``  |
|                          |                         |parameter to make an     |
|                          |                         |initial limited request  |
|                          |                         |and use the ID of the    |
|                          |                         |last-seen item from the  |
|                          |                         |response as the          |
|                          |                         |``marker`` parameter     |
|                          |                         |value in a subsequent    |
|                          |                         |limited request.         |
+--------------------------+-------------------------+-------------------------+

This operation does not accept a request body.




Response
""""""""""""""""

This table shows the body parameters for the response:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|**snapshot**              |Dict                     |A snapshot object.       |
+--------------------------+-------------------------+-------------------------+
|snapshot.\ **status**     |String                   |The snapshot status.     |
+--------------------------+-------------------------+-------------------------+
|snapshot.\                |String                   |The snapshot description.|
|**description**           |                         |                         |
+--------------------------+-------------------------+-------------------------+ 
|snapshot.\                |DateTime                 |The date and time when   |
|**created_at**            |                         |the snapshot was created.|
|                          |                         |The format is ISO8601.   |
|                          |                         |For example,             |
|                          |                         |CCYY-MM-DD-Thh:mm:ss+/-  |
|                          |                         |hh:mm. The +/- value, if |
|                          |                         |included, is the time    |
|                          |                         |zone as an offset from   |
|                          |                         |UTC.                     |
+--------------------------+-------------------------+-------------------------+
|snapshot.\                |Dict                     |One or more metadata key |
|**metadata**              |                         |and value pairs that are |
|                          |                         |associated with the      |
|                          |                         |snapshot, if any.        |
+--------------------------+-------------------------+-------------------------+
|snapshot.\                |UUID                     |The UUID of the volume   |
|**volume_id**             |                         |if the snapshot was      |
|                          |                         |created from a volume.   |
+--------------------------+-------------------------+-------------------------+
|snapshot.\ **size**       |Integer                  |The size of the volume,  |
|                          |                         |in gibibytes (GiB).      |  
+--------------------------+-------------------------+-------------------------+
|snapshot.\ **id**         |UUID                     |The snapshot UUID.       |
+--------------------------+-------------------------+-------------------------+
|snapshot.\ **name**       |String                   |The snapshot name.       |
+--------------------------+-------------------------+-------------------------+














**Example List snapshots: JSON response**


.. code::

   {
       "snapshots": [
           {
               "status": "available",
               "metadata": {
                   "name": "test"
               },
               "name": "test-volume-snapshot",
               "volume_id": "173f7b48-c4c1-4e70-9acc-086b39073506",
               "created_at": "2015-11-29T02:25:51.000000",
               "size": 1,
               "id": "b1323cda-8e4b-41c1-afc5-2fc791809c8c",
               "description": "volume snapshot"
           }
       ]
   }   




