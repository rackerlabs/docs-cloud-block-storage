
.. _get-an-ssl-certificate:

Retrieve an SSL certificate
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    GET /admin/ssl_certificate/{domain_name}

This operation retrieves an SSL certificate.



The following table shows the successful response code for this operation.


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |OK                       |Success.                 |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""




This table shows the URI parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|{domain_name}             |String *(Required)*      |Specifies a string       |
|                          |                         |representing the type of |
|                          |                         |the SSL certificate,     |
|                          |                         |such as                  |
|                          |                         |``www.example.com``.     |
+--------------------------+-------------------------+-------------------------+





This operation does not accept a request body.




**Example: Retrieve an SSL certificate HTTP request**


.. code::

   GET /v1.0/110011/ssl_certificate/{domain_name} HTTP/1.1
   Host: global.cdn.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217
   Accept: application/json
   Content-type: application/json






Response
""""""""""""""""





This table shows the body parameters for the response:

+------------------------------------------------+-------+---------------------------------------------+
|Name                                            |Type   |Description                                  |
+================================================+=======+=============================================+
|\ **flavor_id**                                 |String |Specifies the CDN-provider flavor id used.   |
+------------------------------------------------+-------+---------------------------------------------+
|\ **domain_name**                               |String |Specifies a string that represents the type  |
|                                                |       |of the SSL certificate, such as              |
|                                                |       |``www.example.com``.                         |
+------------------------------------------------+-------+---------------------------------------------+
|\ **cert_type**                                 |String |Specifies a string representing the type of  |
|                                                |       |the SSL certificate.                         |
+------------------------------------------------+-------+---------------------------------------------+
|\ **cert_details**                              |String |Provides information about the certificate.  |
+------------------------------------------------+-------+---------------------------------------------+
|cert_details.\ **provider**                     |String |Specifies the provider of the certificate.   |
+------------------------------------------------+-------+---------------------------------------------+
|cert_details.provider.\ **cert_domain**         |String |Specifies the certificate domain.            |
+------------------------------------------------+-------+---------------------------------------------+
|cert_details.provider.cert_domain.\             |String |Provides additional information about the    |
|**extra_info**                                  |       |certificate.                                 |
+------------------------------------------------+-------+---------------------------------------------+
|cert_details.provider.cert_domain.extra_info.\  |String |Provides the status the certificate.         |
|**status**                                      |       |                                             |
+------------------------------------------------+-------+---------------------------------------------+
|cert_details.provider.cert_domain.extra_info.\  |String |Provides SAN certification information.      |
|**san_cert**                                    |       |                                             |
+------------------------------------------------+-------+---------------------------------------------+
|cert_details.provider.cert_domain.extra_info.\  |String |Provides information about any action for    |
|**action**                                      |       |the certificate.                             |
+------------------------------------------------+-------+---------------------------------------------+
|\ **status**                                    |String |Provides status information for the          |
|                                                |       |certificate.                                 |
+------------------------------------------------+-------+---------------------------------------------+
|\ **project_id**                                |String |Provides the project ID for the certificate. |
+------------------------------------------------+-------+---------------------------------------------+





**Example: Retrieve an SSL certificate JSON response**


.. code::

   HTTP/1.1 200 OK
   Content-Type: application/json


.. code::

           [
             {
               "flavor_id": "cdn",
               "domain_name": "www.mydomain.com",
               "cert_type": "san",
               "cert_details": {
                 "provider": {
                   "cert_domain": null,
                   "extra_info": {
                     "status": "create_in_progress",
                     "san cert": null,
                     "action": "Waiting for action"
                   }
                 }
               },
               "status": "create_in_progress",
               "project_id": "110011"           
          ]
