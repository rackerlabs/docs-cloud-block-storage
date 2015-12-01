.. _gsg-delete-volume:

Delete a volume
~~~~~~~~~~~~~~~~~~~~

To delete a volume when it is no longer in use and the data that it
contains is not needed, send a **DELETE** request that includes the
volume ID.

..  note:: 
    Deleting a volume deletes all the data within it. You cannot recover the
    data unless it is backed up before the volume is deleted.

The HTTP request must include a header to specify the authentication
token.

The cURL request uses the ``-i`` option to include the HTTP headers in
the output and the ``-X`` option to specify the HTTP method to use
(instead of using the default).

An HTTP status code of 202 (Accepted) in the response indicates that the
delete request has been accepted for processing and the volume will be
deleted.

 
**Example: Delete volume: cURL**

.. code::  

   curl -i -X DELETE https://dfw.blockstorage.api.rackspacecloud.com/v1/yourAccountID/volumes/yourVolumeID \
   -H "X-Auth-Token: yourAuthToken" \
   -H "Content-Type: application/json" 

.. code::  

   HTTP/1.1 202 Accepted
   Content-Type: text/html; charset=UTF-8
   Content-Length: 0
   Date: Wed, 04 Jun 2014 19:17:35 GMT
