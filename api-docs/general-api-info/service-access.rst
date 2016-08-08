.. _service-access:

========================
Service access endpoints
========================

The Cloud Block Storage service is a regionalized service. The user of
the service is therefore responsible for appropriate replication,
caching, and overall maintenance of Cloud Block Storage data across
regional boundaries to other Cloud Block Storage servers.

The following table lists the |product name| endpoints that are available
for each region.

.. tip::
   To help you decide which regionalized endpoint to use, read about
   :how-to:`special considerations for choosing a region <about-regions>`.

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

Replace the sample account ID number, ``123456``, with your actual account number
that is returned as part of the
:ref:`authentication response<review-auth-resp>`. The account number is
located  after the  final slash (/) in the ``publicURL`` field.

