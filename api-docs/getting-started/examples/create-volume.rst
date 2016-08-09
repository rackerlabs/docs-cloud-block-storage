.. _gsg-create-volume:

Creating a block storage volume 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Your first step in Cloud Block Storage is to create a volume. To do
this, send a **POST** request.

The HTTP request must include a header to specify the authentication
token.

An HTTP status code of ``200 (OK)`` in the response indicates that the
volume was successfully created.

..  note::
    You use the ``source_volid`` parameter for volume cloning, which has
    some limitations. You cannot create more than one clone per volume
    concurrently. Snapshots and volume cloning use the same locking
    mechanism, so you cannot run a snapshot and a clone of the same volume
    concurrently.

**Example: cURL create a volume request**

.. code:: bash

   curl -i -X POST $API_ENDPOINT/v1/$TENANT_ID/volumes -d \
    '{
    "volume":{
    "display_name": "vol-001",
    "size": 100
    }
     }' \
    -H "X-Auth-Token: $AUTH_TOKEN" \
    -H "Content-Type: application/json"

**Example: Create a volume response**

.. code:: json

   HTTP/1.1 200 OK
   X-Compute-Request-Id: req-2af6c97a-2397-4e52-a0d0-4fde64cfb88c
   Content-Type: application/json
   Content-Length: 399
   Date: Tue, 03 Jun 2014 21:45:46 GMT
    {
      "volume": {
        "status": "available",
        "display_name": "vol-001",
        "attachments": [

        ],
        "availability_zone": "nova",
        "bootable": "false",
        "created_at": "2014-06-03T21:45:45.000000",
        "display_description": null,
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

..  note::
    You use the ``os-volume_attachments`` API call
    (``/servers/{server_id}/os-volume_attachments``) to attach the new
    volume to your Next Generation Cloud Server (with the specified
    ``{server_id}``). For details, see the `Next Generation Cloud Servers API reference`_.

After the volume is attached, the new volume appears as another device
on the Next Generation Cloud Server. The volume can then be partitioned,
formatted, and mounted for use on the system.

.. _Next Generation Cloud Servers API reference: https://developer.rackspace.com/docs/cloud-servers/v2/api-reference/svr-basic-operations/#attach-volume-to-server