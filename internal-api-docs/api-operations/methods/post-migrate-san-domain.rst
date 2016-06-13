
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

.. _post-migrate-san-domain-admin-provider-akamai-service:

Migrate SAN domain
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    POST //admin/provider/akamai/service

Updates the domain with a new SAN URL.

This operation updates the domain with a new SAN URL.

.. note::
   This endpoint is accessible only by users with the ``support`` role in their Cloud Identity service catalog.
   
   



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |OK                       |Success.                 |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""








This table shows the body parameters for the request:

+-----------------+-----------------+------------------------------------------+
|Name             |Type             |Description                               |
+=================+=================+==========================================+
|\ **project_id** |String           |Specifies the associated identifier for   |
|                 |*(Required)*     |the user account, such as, 12345.         |
+-----------------+-----------------+------------------------------------------+
|\ **service_id** |String           |Specifies the id of the service, such as  |
|                 |*(Required)*     |``96737ae3-cfc1-4c72-be88-5d0e7cc9a3f0``. |
+-----------------+-----------------+------------------------------------------+
|\ **domain_name**|String           |Specifies a string representing the       |
|                 |*(Required)*     |domain, such as ``www.example.com``.      |
+-----------------+-----------------+------------------------------------------+
|\ **new_cert**   |String           |Specifies the new certificate, such as    |
|                 |*(Required)*     |``scdn1.secure6.raxcdn.com.edgekey.net``. |
+-----------------+-----------------+------------------------------------------+
|\ **cert_status**|String           |Specifies the status of the certificate.  |
|                 |*(Required)*     |The default value is ``deployed``. The    |
|                 |                 |other possible value is                   |
|                 |                 |``create_in_progress``.                   |
+-----------------+-----------------+------------------------------------------+





**Example Migrate SAN domain: JSON request**


.. code::

   POST /v1.0/110011/admin/provider/akamai/service HTTP1.1
   Host: global.cdn.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217
   Accept: application/json
   Content-type: application/json
   


.. code::

   {
       "project_id": "12345",
       "service_id": "abcdef",
       "domain_name": "www.mywebsite.com",
       "new_cert": "scdn1.secure6.raxcdn.com.edgekey.net",
       "cert_status": "deployed"
   }





Response
""""""""""""""""










**Example Migrate SAN domain: JSON response**


.. code::

   HTP/1.1 202 (Accepted)




