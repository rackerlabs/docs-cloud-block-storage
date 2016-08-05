.. _gsg-update-snapshot:

Updating a snapshot
~~~~~~~~~~~~~~~~~~~

To modify a snapshot’s name, description, or both, send a **PUT**
request that includes the snapshot ID.

The HTTP request must include a header to specify the authentication
token.

An HTTP status code of ``200 (OK)`` in the response indicates that the
request successfully completed.

 
**Example: cURL update a snapshot request**

.. code:: bash

   curl -i -X PUT $API_ENDPOINT/v1/$TENANT_ID/snapshots/yourSnapshotID  -d \
      '{
       "snapshot":{
           "display_name":"newSnapshotName",
           "display_description":"newSnapshotDescription"
           }
       }' \
       -H "X-Auth-Token: $AUTH_TOKEN" \
       -H "Content-Type: application/json"

**Example: Update a snapshot response**

.. code:: json

   HTTP/1.1 200 OK
   X-Compute-Request-Id: req-8a131657-46a3-435b-bee4-b612c79c8c09
   Content-Length: 358
   Content-Type: text/html; charset=UTF-8
   Date: Wed, 04 Jun 2014 20:59:12 GMT

    {
      "snapshot": {
        "created_at" : "2014-06-04T20:13:34.000000",
        "status": "available",
        "display_name": "newSnapshotName",
        "display_description": "newSnapshotDescription",
        "id": "a3df5c35-3218-436e-b706-c85edc3f149d",
        "size": 100,
        "volume_id" : "1a036384-99b2-4fed-ac05-31f964d6925d"
      }
    }
