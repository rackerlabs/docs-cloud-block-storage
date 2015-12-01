.. _gsg-update-volume:

Update a volume
~~~~~~~~~~~~~~~~~~~~

To modify a volume’s name, description, or both, send a **PUT** request
that includes the volume ID.

The HTTP request must include a header to specify the authentication
token.

The cURL request uses the ``-i`` option to include the HTTP headers in
the output, the ``-X`` option to specify the HTTP method to use (instead
of using the default ), and the ``-d`` option to send data in the
request to the HTTP server.

An HTTP status code of 200 (OK) in the response indicates that the
request successfully completed.

 
**Example: Update volume: cURL**

.. code::  

   curl -i -X PUT -d \
      '{
       "volume":{
           "display_name":"newName",
           "display_description":"newDescription"
           }
       }'\
       -H "X-Auth-Token: yourAuthToken" \
       -H "Content-Type: application/json" \
       https://dfw.blockstorage.api.rackspacecloud.com/v1/yourAccountID/volumes/yourVolumeID

.. code::  

   HTTP/1.1 200 OK
   X-Compute-Request-Id: req-8a131657-46a3-435b-bee4-b612c79c8c09
   Content-Type: application/json
   Content-Length: 411
   Date: Wed, 04 Jun 2014 18:29:43 GMT

    { 
      "volume": {
        "status": "available",
        "display_name": "newName",
        "attachments": [
          
        ],
        "availability_zone": "nova",
        "bootable": "false",
        "created_at": "2014-06-03T21:45:45.000000",
        "display_description": "newDescription",
        "volume_type": "SATA",
        "snapshot_id": null,
        "source_volid": null,
        "metadata": {
          "storage-node": "3d0a6f43-d1d9-4fea-bffa-8cf9fc7bf7e8"
        },
        "id": "a3df5c35-3218-436e-b706-c85edc3f149d",
        "size": 100
      }
    } 
