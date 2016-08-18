
.. _support-verify-privliges:

Retrieve health check
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

   curl -H "Content-Type: application/json" -X POST -d '
        {
         "auth": {
         "RAX-AUTH:domain": {
         "name": "Rackspace"
         },
         "RAX-AUTH:rsaCredentials": {
         "username": "<SSO_USERNAME>",
         "tokenKey": "<RSA TOKEN>"
         }
         }
        }' https://identity-internal.api.rackspacecloud.com/v2.0/tokens | python -m json.tool


Look for the cbs_support role. If you do not have this role, you will not be able to take advantage of the additional features.


For further information about Rackspace authentication, please see documentation for the identity Rackspace Auth Extension
