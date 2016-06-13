
.. _post-create-flavors-flavors:

Create flavors
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    POST /flavors



This operation creates flavors.



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|201                       |Created                  |Following a POST         |
|                          |                         |command, this status     |
|                          |                         |indicates success. The   |
|                          |                         |request has been         |
|                          |                         |fulfilled and resulted   |
|                          |                         |in a new resource being  |
|                          |                         |created.                 |
+--------------------------+-------------------------+-------------------------+
|400                       |Bad Request              |Invalid json.            |
+--------------------------+-------------------------+-------------------------+
|400                       |Bad Request              |Invalid url format in    |
|                          |                         |href.                    |
+--------------------------+-------------------------+-------------------------+
|400                       |Bad Request              |Missing provider ID.     |
+--------------------------+-------------------------+-------------------------+
|400                       |Bad Request              |Missing provider-url     |
|                          |                         |entry.                   |
+--------------------------+-------------------------+-------------------------+
|400                       |Bad Request              |Missing rel parameter.   |
+--------------------------+-------------------------+-------------------------+
|400                       |Bad Request              |Provider ID is greater   |
|                          |                         |than 64 bytes.           |
+--------------------------+-------------------------+-------------------------+
|400                       |Bad Request              |Providers ['links'] list |
|                          |                         |is empty.                |
+--------------------------+-------------------------+-------------------------+
|400                       |Bad Request              |Providers list is empty. |
+--------------------------+-------------------------+-------------------------+
|400                       |Bad Request              |Providers name is        |
|                          |                         |greater than 64 bytes.   |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""








This table shows the body parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|\ **id**                  |String *(Required)*      |Specifies the name of    |
|                          |                         |the flavor. The name     |
|                          |                         |must not exceed 64 bytes |
|                          |                         |in length and is limited |
|                          |                         |to unicode, digits,      |
|                          |                         |underscores, and hyphens.|
+--------------------------+-------------------------+-------------------------+
|\ **providers**           |String *(Required)*      |Specifies the list of    |
|                          |                         |providers mapped to this |
|                          |                         |flavor class.            |
+--------------------------+-------------------------+-------------------------+
|providers.\               |String *(Required)*      |Specifies the name of    |
|**provider**              |                         |the provider. The name   |
|                          |                         |must not exceed 64 bytes |
|                          |                         |in length and is limited |
|                          |                         |to unicode, digits,      |
|                          |                         |underscores, and hyphens.|
+--------------------------+-------------------------+-------------------------+
|providers.\ **links**     |String *(Required)*      |Specifies a list with a  |
|                          |                         |``href`` where ``rel``   |
|                          |                         |is ``provider_url``.     |
|                          |                         |Rackspace CDN ignores    |
|                          |                         |all entries in the list  |
|                          |                         |except ``provider_url``. |
+--------------------------+-------------------------+-------------------------+





**Example: Create flavors JSON request**


.. code::

   POST /v1.0/110011/flavors HTTP/1.1
   Host: global.cdn.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217
   Accept: application/json
   Content-type: application/json
   


.. code::

   {
       "id": "cdn",
       "providers": [
           {
               "provider": "akamai",
               "links": [
                   {
                       "href": "http://www.akamai.com",
                       "rel": "provider_url"
                   }
               ]
           }
       ]
   }





Response
""""""""""""""""





This table shows the body parameters for the response:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|\ **id**                  |String                   |Specifies the name of    |
|                          |                         |the flavor. The name     |
|                          |                         |must not exceed 64 bytes |
|                          |                         |in length and is limited |
|                          |                         |to unicode, digits,      |
|                          |                         |underscores, and hyphens.|
+--------------------------+-------------------------+-------------------------+
|\ **providers**           |String                   |Specifies the list of    |
|                          |                         |providers mapped to this |
|                          |                         |flavor class.            |
+--------------------------+-------------------------+-------------------------+
|providers.\               |String                   |Specifies the name of    |
|**provider**              |                         |the provider. The name   |
|                          |                         |must not exceed 64 bytes |
|                          |                         |in length and is limited |
|                          |                         |to unicode, digits,      |
|                          |                         |underscores, and hyphens.|
+--------------------------+-------------------------+-------------------------+
|providers.\ **links**     |String                   |Specifies a list with a  |
|                          |                         |``href`` where ``rel``   |
|                          |                         |is ``provider_url``.     |
|                          |                         |Rackspace CDN ignores    |
|                          |                         |all entries in the list  |
|                          |                         |except ``provider_url``. |
+--------------------------+-------------------------+-------------------------+







**Example: Create flavors JSON response**


.. code::

   HTP/1.1 201 (Created)
   Location: https://global.cdn.api.rackspacecloud.com/v1.0/flavors/cdn


.. code::

   {
       "id": "cdn",
       "providers": [
           {
               "provider": "akamai",
               "links": [
                   {
                       "href": "http://www.akamai.com",
                       "rel": "provider_url"
                   }
               ]
           }
       ]
   }




