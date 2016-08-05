.. _gsg-delete-snapshot:

Deleting a snapshot
~~~~~~~~~~~~~~~~~~~~

To delete a snapshot, send a **DELETE** request that includes the
snapshot ID.

The HTTP request must include a header to specify the authentication
token.

An HTTP status code of ``202 (Accepted)`` in the response indicates that the
delete request has been accepted for processing and the snapshot will be
deleted.

**Example: cURL delete a snapshot request**

.. code:: bash

   curl -i -X DELETE $API_ENDPOINT/v1/$TENANT_ID/snapshots/yourSnapshotID \
   -H "X-Auth-Token: $AUTH_TOKEN" \
   -H "Content-Type: application/json"

**Example: Delete a snapshot response**

.. code::  json

   HTTP/1.1 202 Accepted
   Content-Type: text/html; charset=UTF-8
   Content-Length: 0
   Date: Wed, 04 Jun 2014 21:09:15 GMT
