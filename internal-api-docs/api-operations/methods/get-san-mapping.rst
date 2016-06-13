
.. _get-san-mapping:

Retrieve the SAN-mapping list for the Akamai-related background job
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    GET /admin/provider/akamai/background_job/san_mapping



This operation retrieves the SAN-mapping for an Akamai-related background job.   
   
   
   
   



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |OK                       |Success.                 |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""

This operation does not require a request body.










**Example: Retrieve the SAN-mapping for the Akamai-related background job HTTP request**


.. code::

   GET /v1.0/110011/admin/provider/akamai/background_job/san-mapping HTTP/1.1
   Host: global.cdn.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217
   Accept: application/json
   Content-type: application/json
   

   







Response
""""""""""""""""


This table shows the body parameters for the response:


+------------------+-------------+---------------------------------------------+
|\ **domain_name** |String       |Specifies a string representing the          |
|                  |*(Required)* |customer's domain name, such as              |
|                  |             |``testabc.cnamecdn.com``.                    |
+------------------+-------------+---------------------------------------------+
|\ **san_cert**    |String       |Specifies the SAN certificate CNAME, to which|
|                  |*(Required)* |the customer is mapping, for example,        |    
|                  |             |``secure1.san1.altcdn.com``.                 |
+------------------+-------------+---------------------------------------------+







**Example: Retrieve the SAN-mapping list for the Akamai-related background job JSON response**


.. code::

   HTP/1.1 2020 (OK)


.. code::

   [ 
      {
        "domain_name": "test-san1.cnamecdn.com",
        "san_cert_name": "san1.sample.com"
      },
      {
        "domain_name": "test-san2.cnamecdn.com",
        "san_cert_name": "san2.sample.com"
      }
   ]


