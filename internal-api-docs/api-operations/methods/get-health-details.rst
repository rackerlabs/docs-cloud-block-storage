
.. _get-health-details:

Retrieve health details
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    GET /admin/health/{subsystem}


This operation shows whether a subsystem is online or offline. 



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




This table shows the URI parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|{subsystem}               |String (*Required*)      |The unique identifier    |
|                          |                         |for the user.            |
+--------------------------+-------------------------+-------------------------+





This operation does not accept a request body.




**Example: Retrieve health details HTTP request**


.. code::

   GET /v1.0/110011/health/{subsystem} HTTP1.1
   Host: global.cdn.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217
   Accept: application/json
   Content-type: application/json
   





Response
""""""""""""""""










**Example: Retrieve health details 200 response**


.. code::

   HTTP/1.1 200 OK
   Content-Type: application/json


.. code::

   {
       "online": true
   }




**Example: Retrieve health details 503 response**


.. code::

   HTTP/1.0 503 Service Unavailable
   Content-Type: application/json


.. code::

   {
       "online": false
   }




