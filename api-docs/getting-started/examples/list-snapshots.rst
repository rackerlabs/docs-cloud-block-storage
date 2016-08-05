.. _gsg-list-snapshots:

Listing snapshots 
~~~~~~~~~~~~~~~~~

To list all of the snapshots that you have created in a single region,
send a **GET** request.

The HTTP request must include a header to specify the authentication
token.

An HTTP status code of ``200 (OK)`` in the response indicates that the
request successfully completed.

**Example: cURL list snapshots request**

.. code:: bash

   curl -i -X GET $API_ENDPOINT/v1/$TENANT_ID/snapshots \
   -H "X-Auth-Token: $AUTH_TOKEN" \
   -H "Content-Type: application/json"

**Example: List snapshots response**

.. code:: json

   HTTP/1.1 200 OK
   X-Compute-Request-Id: req-1a938da7-cf74-4ac6-a72f-4c927ae23605
   Content-Type: application/json
   Content-Length: 541
   Date: Wed, 04 Jun 2014 20:28:01 GMT

     {
      "snapshots": [
        {
          "status": "creating",
          "display_name": "snap-001",
          "created_at": "2014-06-04T20:16:17.000000",
          "display_description": "Daily Backup",
          "volume_id": "c849a193-5275-4527-9e5a-69b2a05933aa",
          "metadata": {

          },
          "id": "a6211a94-937f-4770-8dae-1813cb643213",
          "size": 100
        },
        {
          "status": "available",
          "display_name": "snap-002",
          "created_at": "2014-06-04T20:13:34.000000",
          "display_description": "Weekly Backup",
          "volume_id": "1a036384-99b2-4fed-ac05-31f964d6925d",
          "metadata": {

          },
          "id": "ca320eb7-b371-4dbe-b2e9-2543c952f507",
          "size": 100
        }
      ]
    }
