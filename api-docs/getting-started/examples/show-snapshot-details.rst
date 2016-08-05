.. _gsg-show-snapshot-details:

Showing snapshot details
~~~~~~~~~~~~~~~~~~~~~~~~

To show details about a specified snapshot, send a **GET** request that
includes the snapshot ID.

The HTTP request must include a header to specify the authentication
token.

An HTTP status code of ``200 (OK)`` in the response indicates that the
request successfully completed.

..  note::
    ``os-extended-snapshot-attributes:progress`` in the response body shows
    snapshot creation progress.

**Example: cURL show snapshot details request**

.. code:: bash

   curl -i -X GET $API_ENDPOINT/v1/$TENANT_ID/snapshots/yourSnapshotID \
   -H "X-Auth-Token: $AUTH_TOKEN" \
   -H "Content-Type: application/json"

**Example: Show snapshot details response**

.. code:: json

   HTTP/1.1 200 OK
   X-Compute-Request-Id: req-7314746b-0670-4160-b6a7-388cafbfd082
   Content-Type: application/json
   Content-Length: 383
   Date: Wed, 04 Jun 2014 20:47:48 GMT

   {
      "snapshot": {
        "status": "available",
        "display_name": "snap-002",
        "created_at": "2014-06-04T20:13:34.000000",
        "display_description": "Weekly Backup",
        "os-extended-snapshot-attributes:progress": "100%",
        "volume_id": "1a036384-99b2-4fed-ac05-31f964d6925d",
        "os-extended-snapshot-attributes:project_id": "yourAccountID",
        "metadata": {

        },
        "id": "ca320eb7-b371-4dbe-b2e9-2543c952f507",
        "size": 100
      }
    }
