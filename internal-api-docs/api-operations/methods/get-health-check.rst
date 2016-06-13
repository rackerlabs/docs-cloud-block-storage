
.. _get-health-check:

Retrieve health check
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    GET /admin/health


This operation retrieves a health check. 



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |OK                       |Success.                 |
+--------------------------+-------------------------+-------------------------+
|503                       |Service Unavailable      |The service is           |
|                          |                         |temporarily unavailable  |
|                          |                         |(for example, for        |
|                          |                         |scheduled platform       |
|                          |                         |maintenance). Try again  |
|                          |                         |later.                   |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""








This operation does not accept a request body.




**Example: Retrieve health check HTTP request**


.. code::

   GET /v1.0/110011/health HTTP/1.1
   Host: global.cdn.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217
   Accept:application/json
   Content-type: application/json
   





Response
""""""""""""""""










**Example: Retrieve health check 200 response**


.. code::

   HTTP/1.1 200 OK
   Content-Type: application/json


.. code::

   {
       "storage": {
           "cassandra": {
               "online": true,
               "links": [
                   {
                       "href": "https://global.cdn.api.rackspacecloud.com/v1.0/110011/health/storage/cassandra",
                       "rel": "self"
                   }
               ]
           }
       },
       "transport": {
           "pecan": {
               "online": true,
               "node": "ppy-web-01",
               "links": [
                   {
                       "href": "https://global.cdn.api.rackspacecloud.com/v1.0/110011/health/transport/pecan",
                       "rel": "self"
                   }
               ]
           }
       }
   }


**Example: Retrieve health check 503 response**

.. code::

   HTTP/1.1 503 Service Unavailable
   Content-Type: application/json


.. code::

   {
       "storage": {
           "cassandra": {
               "online": false,
               "links": [
                   {
                       "href": "https://global.cdn.api.rackspacecloud.com/v1.0/110011/health/storage/cassandra",
                       "rel": "self"
                   }
               ]
           }
       },
       "transport": {
           "pecan": {
               "online": true,
               "node": "phx-web-01",
               "links": [
                   {
                       "href": "https://global.cdn.api.rackspacecloud.com/v1.0/110011/health/transport/pecan",
                       "rel": "self"
                   }
               ]
           }
       }
   }




