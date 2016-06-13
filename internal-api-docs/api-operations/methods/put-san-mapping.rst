
.. _put-san-mapping:

Update the SAN-mapping list for the Akamai-related background job
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    PUT /admin/provider/akamai/background_job/san_mapping



This operation updates the SAN-mapping for an Akamai-related background job.







This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|202                       |Accepted                 |The request has been     |
|                          |                         |accepted for processing. |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""

This operation does not require a request body.



This table shows the body parameters for the request:


+------------------+-------------+---------------------------------------------+
|\ **domain_name** |String       |Specifies a string representing the          |
|                  |*(Required)* |customer's domain name, such as              |
|                  |             |``testabc.cnamecdn.com``.                    |
+------------------+-------------+---------------------------------------------+
|\ **san_cert**    |String       |Specifies the SAN certificate CNAME, to which|
|                  |*(Required)* |the customer is mapping, for example,        |
|                  |             |``secure1.san1.altcdn.com``.                 |
+------------------+-------------+---------------------------------------------+







**Example: Update the SAN-mapping for the Akamai-related background job JSON request**


.. code::

   PUT /v1.0/110011/admin/provider/akamai/background_job/san-mapping HTTP/1.1
   Host: global.cdn.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217
   Accept: application/json
   Content-type: application/json

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









Response
""""""""""""""""


This table shows the body parameters for the response:


+------------------+-------------+---------------------------------------------+
|\ **queued**      |String       |Specifies a list that includes the domain    |
|                  |             |name and the SAN certificate name to update. |
+------------------+-------------+---------------------------------------------+
|queued.           |String       |Specifies a string representing the          |
|\ **domain_name** |             |customer's domain name, such as              |
|                  |             |``testabc.cnamecdn.com``.                    |
+------------------+-------------+---------------------------------------------+
|queued.           |String       |Specifies the SAN certificate CNAME, to which|
|\ **san_cert**    |             |the customer is mapping, for example,        |
|                  |             |``secure1.san1.altcdn.com``.                 |
+------------------+-------------+---------------------------------------------+
|\ **deleted**     |String       |Specifies a list that includes the domain    |
|                  |             |name and the SAN certificate name to delete. |
+------------------+-------------+---------------------------------------------+
|deleted.          |String       |Specifies a string representing the          |
|\ **domain_name** |             |customer's domain name, such as              |
|                  |             |``testabc.cnamecdn.com``.                    |
+------------------+-------------+---------------------------------------------+
|deleted.          |String       |Specifies the SAN certificate CNAME, to which|
|\ **san_cert**    |             |the customer is mapping, for example,        |
|                  |             |``secure1.san1.altcdn.com``.                 |
+------------------+-------------+---------------------------------------------+







**Example: Retrieve the SAN-mapping list for the Akamai-related background job JSON response**


.. code::

   HTP/1.1 2020 (OK)


.. code::

   {
     "queue": [
       {
         "domain_name": "test-san1.cnamecdn.com",
         "san_cert_name": "san1.sample.com"
       },
       {
         "domain_name": "test-san2.cnamecdn.com",
         "san_cert_name": "san2.sample.com"
       }
     ],
     "deleted": [
       {
         "domain_name": "test-san0.cnamecdn.com",
         "san_cert_name": "san1.sample.com"
       }
     ]
   }
