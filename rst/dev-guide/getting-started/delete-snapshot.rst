.. _gsg-delete-snapshot:

Delete a snapshot
~~~~~~~~~~~~~~~~~~~~

To delete a snapshot, send a **DELETE** request that includes the
snapshot ID.

The HTTP request must include a header to specify the authentication
token.

The cURL request uses the ``-i`` option to include the HTTP headers in
the output and the ``-X`` option to specify the HTTP method to use
(instead of using the default).

An HTTP status code of 202 (Accepted) in the response indicates that the
delete request has been accepted for processing and the snapshot will be
deleted.

 
**Example: Delete a snapshot: cURL**

.. code::  

   curl -i -X DELETE https://dfw.blockstorage.api.rackspacecloud.com/v1/yourAccountID/snapshots/yourSnapshotID \
   -H "X-Auth-Token: yourAuthToken" \
   -H "Content-Type: application/json" 

.. code::  

   HTTP/1.1 202 Accepted
   Content-Type: text/html; charset=UTF-8
   Content-Length: 0
   Date: Wed, 04 Jun 2014 21:09:15 GMT
