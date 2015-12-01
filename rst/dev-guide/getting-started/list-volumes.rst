.. _gsg-list-volumes:

List existing block storage volumes
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To list all of the block storage volumes that you have created in a
single region, send a **GET** request.

The HTTP request must include a header to specify the authentication
token.

The cURL request uses the ``-i`` option to include the HTTP headers in
the output and the ``-X`` option to specify the HTTP method in the
request.

An HTTP status code of 200 (OK) in the response indicates that the
request successfully completed.

 
**Example: List volumes: cURL**

.. code::  

   curl -i -X GET https://dfw.blockstorage.api.rackspacecloud.com/v1/yourAccountID/volumes \
   -H "X-Auth-Token: yourAuthToken" \
   -H "Content-Type: application/json" 

.. code::  

   HTTP/1.1 200 OK
   X-Compute-Request-Id: req-7941b291-f226-459d-9a78-5d38660f3ae7
   Content-Type: application/json
   Content-Length: 1179
   Date: Wed, 04 Jun 2014 16:52:15 GMT  

   { 
      "volumes": [
        {
          "status": "available",
          "display_name": "vol-001",
          "attachments": [
            
          ],
          "availability_zone": "nova",
          "bootable": "false",
          "created_at": " 2014-06-03T21:45:45.000000 ",
          "display_description": null,
          "volume_type": "SATA",
          "snapshot_id": null,
          "source_volid": null,
          "metadata": {
            "storage-node": " 3d0a6f43-d1d9-4fea-bffa-8cf9fc7bf7e8 "
          },
          "id": " a3df5c35-3218-436e-b706-c85edc3f149d ",
          "size": 100
        }
      ]
    } 
