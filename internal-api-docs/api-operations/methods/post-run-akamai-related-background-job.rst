
.. _post-run-akamai-related-background-job:

Run Akamai-related background job
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    POST /admin/provider/akamai/background_job



This operation runs an Akamai-related background job.

.. note::
   The following types of jobs are supported: 
   
   * akamai_update_papi_property_for_mod_san
   * akamai_check_and_update_cert_status
   
   
   
   
   



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|202                       |Accepted                 |The request has been     |
|                          |                         |accepted for processing. |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""








This table shows the body parameters for the request:

+------------------+-------------+---------------------------------------------+
|Name              |Type         |Description                                  |
+==================+=============+=============================================+
|\ **job_type**    |String       |Specifies the type of background job. The    |
|                  |*(Required)* |following types of jobs are supported:       |
|                  |             |``akamai_update_papi_property_for_mod_san``  |
|                  |             |and ``akamai_check_and_update_cert_status``. |
+------------------+-------------+---------------------------------------------+
|\ **updated_cname_|String       |When ``job_type`` is                         |
|host_mapping      |*(Required)* |``akamai_update_papi_property_for_mod_san``, |
|_info**           |             |the list is required and specifies the       |
|                  |             |domain-to-SAN-certificate CNAME mapping.     |
+------------------+-------------+---------------------------------------------+
|updated_cname_host|String       |Specifies a string representing the          |
|host_mapping_info.|*(Required)* |customer's domain name, such as              |
|\ **domain_name** |             |``testabc.cnamecdn.com``.                    |
+------------------+-------------+---------------------------------------------+
|updated_cname_host|String       |Specifies the SAN certificate CNAME, to which|
|host_mapping_info.|*(Required)* |the customer is mapping, for example,        |    
|\ **san_cert      |             |``secure1.san1.altcdn.com``.                 |
|_name**           |             |                                             |
+------------------+-------------+---------------------------------------------+
|updated_cname_host|String       |When ``job_type`` is                         |
|host_mapping_info.|*(Optional)* |``akamai_check_and_update_cert_status``,     |    
|\ **project_id**  |             |specifies the customer's project ID.         |
+------------------+-------------+---------------------------------------------+
|updated_cname_host|String       |When ``job_type`` is                         |
|host_mapping_info.|*(Optional)* |``akamai_check_and_update_cert_status``,     |    
|\ **cert_type**   |             |specifies the customer's certificate type.   |
|                  |             |Currently, the only valid value is ``san``.  |
+------------------+-------------+---------------------------------------------+
|updated_cname_host|String       |When ``job_type`` is                         |
|host_mapping_info.|*(Optional)* |``akamai_check_and_update_cert_status``,     |    
|\ **flavor_id**   |             |specifies the customer's flavor.             |
+------------------+-------------+---------------------------------------------+
|\ **action**      |String       |When ``job_type`` is                         |
|                  |*(Required)* |``akamai_check_and_update_cert_status``,     |
|                  |             |valid values for ``action`` are ``add`` or   |
|                  |             |``remove``.                                  |
+------------------+-------------+---------------------------------------------+



**Example: Run Akamai-related background job JSON request**


.. code::

   POST /v1.0/110011/admin/provider/akamai/background_job HTTP/1.1
   Host: global.cdn.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217
   Accept: application/json
   Content-type: application/json
   


.. code::
    
    {
      "job_type": "akamai_update_papi_property_for_mod_san",
      "update_cname_host_mapping_info": [
        {
          "domain_name": "testabc.testsan.com",
          "san_cert_name": "secure1.san1.testcdn.com"
        }, 
        {
          "domain_name": "testabc2.testsan.com",
          "san_cert_name": "secure2.san1.testcdn.com"
        }
      ],
      "action": "add"
    }    
   







Response
""""""""""""""""










**Example: Run Akamai-related background job HTTP response**


.. code::

   HTP/1.1 202 (Accepted)
   




