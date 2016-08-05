.. _gsg-show-volume-details:

Showing volume details
~~~~~~~~~~~~~~~~~~~~~~

To show details about a specified volume, send a **GET** request that
includes the volume ID.

The HTTP request must include a header to specify the authentication
token.

An HTTP status code of ``200 (OK)`` in the response indicates that the
request successfully completed.

**Example: cURL show volume details request**

.. code:: bash

   curl -i -X GET $API_ENDPOINT/v1/$TENANT_ID/volumes/yourVolumeID \
   -H "X-Auth-Token: $AUTH_TOKEN" \
   -H "Content-Type: application/json"

**Example: Show volume details response**

.. code:: json

   HTTP/1.1 200 OK
   X-Compute-Request-Id: req-0ec1d1e0-c591-47d2-a8e7-9a8923e495b2
   Content-Type: application/json
   Content-Length: 554
   Date: Wed, 04 Jun 2014 18:15:24 GMT

    {
      "volume": {
        "status": "available",
        "display_name": "vol-001",
        "attachments": [

        ],
        "availability_zone": "nova",
        "bootable": "false",
        "created_at": "2014-06-03T21:45:45.000000",
        "os-vol-tenant-attr:tenant_id": "yourAccountID",
        "display_description": null,
        "os-vol-host-attr:host": "lunr",
        "volume_type": "SATA",
        "snapshot_id": null,
        "source_volid": null,
        "os-vol-mig-status-attr:name_id": null,
        "metadata": {
          "storage-node": "3d0a6f43-d1d9-4fea-bffa-8cf9fc7bf7e8"
        },
        "id": "a3df5c35-3218-436e-b706-c85edc3f149d",
        "os-vol-mig-status-attr:migstat": null,
        "size": 100
      }
    }
