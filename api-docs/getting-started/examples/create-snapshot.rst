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

An HTTP status code of ``200 (OK)`` indicates that the request was accepted
and ``"status": "creating"`` indicates that the snapshot is in progress.

 
**Example: cURL create a snapshot request**

.. code:: bash

   curl -i -X POST $API_ENDPOINT/v1/$TENANT_ID/snapshots -d \
      '{
      "snapshot": {
          "display_name": "snap-001",
          "display_description": "Daily Backup",
          "volume_id": "yourVolumeID"
        }
      }'\
      -H "X-Auth-Token: $AUTH_TOKEN" \
      -H "Content-Type: application/json"

**Example: Create a snapshot response**

.. code:: json

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
