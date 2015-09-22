.. _overview:

About the API
-----------------------------------------

Rackspace Cloud Block Storage is a block level storage solution that allows customers to mount drives or volumes to their Rackspace Next Generation Cloud Servers™ and OnMetal™ Cloud Servers. The primary use cases for Cloud Block Storage are to allow you to perform the following tasks:

-  Scale your storage independently from your compute resources.

-  Use high performance storage to serve database or I/O-intensive applications.

Interactions with Cloud Block Storage occur programmatically via the Cloud Block Storage API as described in this developer guide. Cloud Block Storage uses a RESTful (Representational State Transfer) web services interface. Rackspace also provides language-specific SDKs in several popular programming languages. For more information, see the `official SDKs and tools`_.

Rackspace offers both a low cost/gigabyte (GB) option with standard performance for customers who only require more storage and a high performance option that provides increased storage with higher performance (at a higher cost/GB). For more information, see the `Cloud Block Storage product page`_.

Highlights of Rackspace Cloud Block Storage include:

-  Mount a drive to a Cloud Server to scale storage without paying for more compute capability.

-  A high performance option for databases and high performance applications, leveraging solid state drives (SSDs) for speed.

-  A standard speed option using SATA drive for customers who just need additional storage on their Cloud Server.

..  note::
    Cloud Block Storage is an add-on feature to Next Generation Cloud Servers and OnMetal Cloud Servers. Customers may not attach Cloud Block Storage volumes to other instances, like first generation Cloud Servers.

    Cloud Block Storage is multi-tenant rather than dedicated.

    When volumes are destroyed, Rackspace keeps that disk space unavailable until zeros have been written to the space to ensure that data is not accessible by any other customers.

    Cloud Block Storage allows you to create snapshots that you can save, list, and restore.

Cloud Block Storage is built on the OpenStack Cinder project. For more information about OpenStack Cinder, see the `OpenStack Block Storage API v1 Reference`_.

You can find additional details about Cloud Block Storage in the `Cloud Block Storage Getting Started Guide`_. This guide provides step-by-step instructions to enter the necessary URLs or commands to use the Cloud Block Storage API.

For additional information about the Cloud Block Storage service, see the `Cloud Block Storage Overview`_.

Rackspace welcomes feedback, comments, and bug reports at support@rackspacecloud.com. 

.. _official SDKs and tools: https://developer.rackspace.com/sdks

.. _Cloud Block Storage product page: http://www.rackspace.com/cloud/block-storage

.. _OpenStack Block Storage API v1 Reference: http://developer.openstack.org/api-ref-blockstorage-v1.html

.. _Cloud Block Storage Getting Started Guide: http://docs.rackspace.com/cbs/api/v1.0/cbs-getting-started/content/Overview_d1e060.html

.. _Cloud Block Storage Overview: http://www.rackspace.com/knowledge_center/article/cloud-block-storage-overview


.. toctree:: :hidden:
   :maxdepth: 3
   
   additional-resources
   api-contract-changes
   pricing-service-level
