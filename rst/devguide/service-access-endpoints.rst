========================
Service access endpoints
========================

The Cloud Block Storage service is a regionalized service. The user of
the service is therefore responsible for appropriate replication,
caching, and overall maintenance of Cloud Block Storage data across
regional boundaries to other Cloud Block Storage servers.

To help you decide which regionalized endpoint to use, read the
Knowledge Center article about special considerations for choosing a
data center at `About
Regions <http://www.rackspace.com/knowledge_center/article/about-regions>`__.

You can find the available service access/endpoints for Cloud Block
Storage summarized in the table below.

**Table: Regionalized service endpoints**

+-------------------------+---------------------------------------------------+
| Region                  | Endpoint                                          |
+=========================+===================================================+
| Chicago (ORD)           | https://ord.blockstorage.api.rackspacecloud.com   |
|                         | /v1/1234/                                         |
+-------------------------+---------------------------------------------------+
| Dallas/Ft. Worth (DFW)  | https://dfw.blockstorage.api.rackspacecloud.com   |
|                         | /v1/1234/                                         |
+-------------------------+---------------------------------------------------+
| Northern Virginia (IAD) | https://iad.blockstorage.api.rackspacecloud.com   |
|                         | /v1/1234/                                         |
+-------------------------+---------------------------------------------------+
| London (LON)            | https://lon.blockstorage.api.rackspacecloud.com   |
|                         | /v1/1234/                                         |
+-------------------------+---------------------------------------------------+
| Sydney (SYD)            | https://syd.blockstorage.api.rackspacecloud.com   |
|                         | /v1/1234/                                         |
+-------------------------+---------------------------------------------------+
| Hong Kong (HKG)         | https://hkg.blockstorage.api.rackspacecloud.com   |
|                         | /v1/1234/                                         |
+-------------------------+---------------------------------------------------+

Replace the sample account ID number, *``1234``*, with your actual
account number returned as part of the authentication service response.

You will find the actual account number after the final '/' in the
``publicURL`` field returned by the authentication response.

