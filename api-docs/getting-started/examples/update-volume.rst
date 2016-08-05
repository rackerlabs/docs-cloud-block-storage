.. _gsg-update-volume:

Updating a volume
~~~~~~~~~~~~~~~~~

To modify a volume’s name, description, or both, send a **PUT** request
that includes the volume ID.

The HTTP request must include a header to specify the authentication
token.

An HTTP status code of ``200 (OK)`` in the response indicates that the
request successfully completed.

**Example: cURL update a volume request**

.. code:: bash

   curl -i -X PUT $API_ENDPOINT/v1/$TENANT_ID/volumes/yourVolumeID -d \
      '{
       "volume":{
           "display_name":"newName",
           "display_description":"newDescription"
           }
       }'\
       -H "X-Auth-Token: $AUTH_TOKEN" \
       -H "Content-Type: application/json"
       
**Example: Update a volume response**

.. code:: json

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
