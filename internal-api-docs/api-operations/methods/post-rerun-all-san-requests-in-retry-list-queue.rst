
.. _post-rerun-all-the-san-requests-in-retry-list-queue:

Rerun all the SAN requests in the retry list queue
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    POST /admin/provider/akamai/ssl_certificate/retry_list


This operation reruns all of the SAN requests in the SAN retry list queue.

.. note::
   This endpoint is accessible only by users with the ``support`` role in their Cloud Identity service catalog.
   
   



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|202                       |Accepted                 |The request has been     |
|                          |                         |accepted for processing..|
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""








This operation does not accept a request body.




**Example: Rerun all the SAN requests in the retry list queue HTTP request**


.. code::

   POST /v1.0/110011/admin/provider/akamai/ssl_certificate/retry_list HTTP/1.1
   Host: global.cdn.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217
   Accept: application/json
   Content-type: application/json





Response
""""""""""""""""










**Example: Rerun all the SAN requests in the retry list queue HTTP response**


.. code::

   HTP/1.1 202 (Accepted)




