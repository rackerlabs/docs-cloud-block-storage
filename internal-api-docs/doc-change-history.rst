.. _doc-change-history:

.. Keeping this file in case you want to use it.

Document change history
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This version of the Developer Guide for Service Management replaces and 
obsoletes all earlier versions. 

The following table describes the most recent changes.

+--------------------------+--------------------------------------------------+
| Revision date            | Summary of changes                               |
+--------------------------+--------------------------------------------------+
| May 31, 2016             | -  Added the ``project_id`` parameter to the     |
|                          |    response for the :ref:`Retrieve an SSL        |
|                          |    certificate <get-an-ssl-certificate>`         | 
|                          |    operation.                                    |                                                 
+--------------------------+--------------------------------------------------+
| April 20, 2016           | -  Changed all of the values for ``flavor_id`` in|                                                  
|                          |    the operation descriptions to ``cdn``.        |
+--------------------------+--------------------------------------------------+
| March 23, 2016           | -  Added the operation to update the SAN         |
|                          |    certificate configuration information to      |
|                          |    :ref:`SAN certificate configuration           |
|                          |    information operations                        |
|                          |    <SAN-cert-config-operations>`, which includes |
|                          |    the following request body parameters:        |
|                          |                                                  |
|                          |    -  The ``spsid`` parameter to configure the   |
|                          |       Secure Provisioning Service (SPS) ID.      |
|                          |                                                  |
|                          |    -  The ``enabled`` parameter to indicate if   |
|                          |       the SAN certificate is enabled and         |
|                          |       disabled.                                  |                                                 
|                          |                                                  |
|                          | -  Updated the operation to get the SAN          |
|                          |    certificate configuration information in      |
|                          |    :ref:`SAN certificate configuration           |
|                          |    information operations                        |
|                          |    <SAN-cert-config-operations>` to include the  |
|                          |    ``enabled`` parameter to indicate if the SAN  |
|                          |    certificate is enabled and disabled.          |
|                          |                                                  |
|                          | -  Updated the operation to run an Akamai        |
|                          |    background job in :ref:`Akamai-related        |
|                          |    background job operations                     |
|                          |    <akamai—background-job-operations>` to include|
|                          |    an information map for the SAN certificate in |
|                          |    the request body.                             |
|                          |                                                  |
|                          | -  Added the following operations operation to   |
|                          |    :ref:`Akamai-related                          |
|                          |    background job operations                     |
|                          |    <akamai—background-job-operations>`:          |
|                          |                                                  |
|                          |    -  GET a SAN-mapping list for a related       |
|                          |       background job to update the papi property.|
|                          |                                                  |
|                          |    -  PUT a SAN-mapping list for a related       |
|                          |       background job to update the papi property.|       
+--------------------------+--------------------------------------------------+
| March 7, 2016            | -  Added the operation to set the status of a    |
|                          |    service to :ref:`Service status operations    |
|                          |    <service-status-operations>`.                 |                                                  
|                          |                                                  |
|                          | -  Added the operation to get domains by the     |
|                          |    provider URL to :ref:`Domains operations      |
|                          |    <domains-operations>`.                        |
|                          |                                                  |
|                          | -  Added the operation to get the SAN certificate|
|                          |    configuration information to :ref:`SAN        |
|                          |    certificate configuration information         |
|                          |    operations <SAN-cert-config-operations>`.     |
+--------------------------+--------------------------------------------------+
| February 8, 2016         | -  Added the following operations for the        |
|                          |    :ref:`SAN retry list operations               |
|                          |    <SAN—retry-list-operations>`:                 |
|                          |                                                  |
|                          |    -  List SAN requests in retry list queue      |
|                          |                                                  |
|                          |    -  Put a SAN request list into the retry list |
|                          |       queue                                      |
|                          |                                                  |
|                          |    -  Rerun all the SAN requests in the retry    |
|                          |       list queue                                 |
|                          |                                                  |
|                          | -  Removed the operation to create an SSL        |
|                          |    certificate from this guide and moved it to   |
|                          |    the external Developer Guide.                 |
+--------------------------+--------------------------------------------------+
| January 14, 2016         | -  Removed the operation to delete an SSL        |
|                          |    certificate from this guide and moved it to   |
|                          |    the external Developer Guide.                 |
+--------------------------+--------------------------------------------------+
| October 27, 2015         | -  Separated administration operations into the  |
|                          |    following sections:                           |
|                          |                                                  |
|                          |    -  :ref:`Service action operations            |
|                          |       <service-action-operations>`               |
|                          |                                                  |
|                          |    -  :ref:`Limits operations                    |
|                          |       <limits-operations>`                       |
|                          |                                                  |
|                          |    -  :ref:`Domains operations                   |
|                          |       <domains-operations>`                      |
|                          |                                                  |
|                          |    -  :ref:`Migrate SAN domain operations        |
|                          |       <migrate—SAN-domain-operations>`           |
|                          |                                                  |
|                          |    -  :ref:`Akamai-related background job        |
|                          |       operations                                 |
|                          |       <akamai—background-job-operations>`        |
|                          |                                                  |
|                          | -  Added the following operations to             |
|                          |    :REF:`Limits operations <limits-operations>`: |
|                          |                                                  |
|                          |    -  Set limits on services for a user account  |
|                          |                                                  |
|                          |    -  Get limits on services for a user account  |
|                          |                                                  |
|                          | -  Added the :ref:`SSL certification operations  |
|                          |    <ssl—certificate-operations>`,                |
|                          |    which includes the following operations:      |
|                          |                                                  |
|                          |    -  Create an SSL certificate                  |
|                          |                                                  |
|                          |    -  Get an SSL certificate                     |
|                          |                                                  |
|                          |    -  Delete an SSL certificate                  |
|                          |                                                  |
|                          | -  Added the following operation to              |
|                          |    :ref:`Akamai-related background job operations|
|                          |    <akamai—background-job-operations>`           |
|                          |                                                  |
|                          |    -  Run Akamai-related background job          |
+--------------------------+--------------------------------------------------+
| August 28, 2015          | -  Added the following operations:               |
|                          |                                                  |
|                          |    -  Post service action                        |
|                          |                                                  |
|                          |    -  Retrieve a service by domain name          |
|                          |                                                  |
|                          |    -  Migrate SAN domain                         |
+--------------------------+--------------------------------------------------+
| April 27, 2015           | -  Initial Unlimited Access (UA) release.        |
+--------------------------+--------------------------------------------------+
| January 7, 2015          | -  Initial Early Access (EA) release.            |
+--------------------------+--------------------------------------------------+
