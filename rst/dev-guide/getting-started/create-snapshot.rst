.. _gsg-create-snapshot:

Creating a snapshot
~~~~~~~~~~~~~~~~~~~~

A snapshot is a point-in-time copy of the data that a volume contains.
You must flush all writes to the volume before you create a snapshot. To
do so, either unmount any file systems on the volume or detach the
volume. Snapshots are incremental, so each time that you create a
snapshot, the incremental changes for the new snapshot are appended to
the previous snapshot, which is still available. Note that you can
create a volume from the snapshot.

To create a snapshot of a block storage volume, send a **POST** request.

The HTTP request must include a header to specify the authentication
token.

The cURL request uses the ``-i`` option to include the HTTP headers in
the output, the ``-X`` option to specify the HTTP method to use (instead
of using the default **GET**), and the ``-d`` option to send data in the
request to the HTTP server.

An HTTP status code of 200 (OK) indicates that the request was accepted
and ``"status": "creating"`` indicates that the snapshot is in progress.

 
**Example: Create a snapshot: cURL**

.. code::  

   curl -i -X POST -d \
      '{
      "snapshot": {
          "display_name": "snap-001",
          "display_description": "Daily Backup",
          "volume_id": "yourVolumeID"
        }
      }'\
      -H "X-Auth-Token: yourAuthToken" \
      -H "Content-Type: application/json" \
     https://dfw.blockstorage.api.rackspacecloud.com/v1/yourAccountID/snapshots 

.. code::  

   HTTP/1.1 200 OK
   X-Compute-Request-Id: req-99d94a3a-1086-4c19-99b4-65d05e2e02f1
   Content-Type: application/json
   Content-Length: 275
   Date: Wed, 04 Jun 2014 20:16:19 GMT

   {
      "snapshot": {
        "status": "creating",
        "display_name": "snap-001",
        "created_at": "2014-06-04T20:16:17.000000",
        "display_description": "Daily Backup",
        "volume_id": "c849a193-5275-4527-9e5a-69b2a05933aa",
        "metadata": {
          
        },
        "id": "a6211a94-937f-4770-8dae-1813cb643213",
        "size": 100
      }
    } 