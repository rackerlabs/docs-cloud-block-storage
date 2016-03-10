.. _service-access-endpoints:

Service access endpoints
~~~~~~~~~~~~~~~~~~~~~~~~

The Cloud Block Storage service is a regionalized service. The user of
the service is therefore responsible for appropriate replication,
caching, and overall maintenance of Cloud Block Storage data across
regional boundaries to other Cloud Block Storage servers.

.. tip::
     To help you decide which regionalized endpoint to use, see the
     considerations for choosing a data center in 
     :how-to:`About regions <about-regions>`.

**Regionalized service endpoints**

+-------------------------+---------------------------------------------------+
| Region                  | Endpoint                                          |
+=========================+===================================================+
| Chicago (ORD)           | https://ord.blockstorage.api.rackspacecloud.com   |
|                         | /v1/123456/                                       |
+-------------------------+---------------------------------------------------+
| Dallas/Ft. Worth (DFW)  | https://dfw.blockstorage.api.rackspacecloud.com   |
|                         | /v1/123456/                                       |
+-------------------------+---------------------------------------------------+
| Northern Virginia (IAD) | https://iad.blockstorage.api.rackspacecloud.com   |
|                         | /v1/123456/                                       |
+-------------------------+---------------------------------------------------+
| London (LON)            | https://lon.blockstorage.api.rackspacecloud.com   |
|                         | /v1/123456/                                       |
+-------------------------+---------------------------------------------------+
| Sydney (SYD)            | https://syd.blockstorage.api.rackspacecloud.com   |
|                         | /v1/123456/                                       |
+-------------------------+---------------------------------------------------+
| Hong Kong (HKG)         | https://hkg.blockstorage.api.rackspacecloud.com   |
|                         | /v1/123456/                                       |
+-------------------------+---------------------------------------------------+

Replace the sample account ID number, ``123456``, with your actual account number, 
which is returned as part of the :ref:`authentication service response<review-auth-resp>`, after the final 
**/** in the ``publicURL`` field.
