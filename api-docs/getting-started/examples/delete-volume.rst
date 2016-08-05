.. _gsg-delete-volume:

Deleting a volume
~~~~~~~~~~~~~~~~~

To delete a volume when it is no longer in use and the data that it
contains is not needed, send a **DELETE** request that includes the
volume ID.

..  note::
    Deleting a volume deletes all the data within it. You cannot recover the
    data unless it is backed up before the volume is deleted.

The HTTP request must include a header to specify the authentication
token.

An HTTP status code of ``202 (Accepted)`` in the response indicates that the
delete request has been accepted for processing and the volume will be
deleted.

**Example: cURL delete a volume request**

.. code:: bash

   curl -i -X DELETE $API_ENDPOINT/v1/$TENANT_ID/volumes/yourVolumeID \
   -H "X-Auth-Token: $AUTH_TOKEN" \
   -H "Content-Type: application/json"

**Example: Delete a volume response**

.. code:: json

   HTTP/1.1 202 Accepted
   Content-Type: text/html; charset=UTF-8
   Content-Length: 0
   Date: Wed, 04 Jun 2014 19:17:35 GMT
