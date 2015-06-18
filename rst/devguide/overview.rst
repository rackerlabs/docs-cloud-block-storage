.. _cbs-dg-overview:

========
Overview
========

Rackspace Cloud Block Storage is a block level storage solution that allows customers to mount drives or volumes to their Rackspace Next Generation Cloud Servers™. The primary use cases for Cloud Block Storage are to allow you to perform the following tasks:

-  Scale your storage independently from your compute resources.

-  Use high performance storage to serve database or I/O-intensive applications.

Interactions with Cloud Block Storage occur programmatically via the Cloud Block Storage API as described in this developer guide. Cloud Block Storage uses a RESTful (Representational State Transfer) web services interface. Rackspace also provides language-specific SDKs in several popular programming languages. For more information, see the `official SDKs and tools`_.

Rackspace offers both a low cost/gigabyte (GB) option with standard performance for customers who only require more storage and a high performance option that provides increased storage with higher performance (at a higher cost/GB). For more information, see the `Cloud Block Storage product page`_.

Highlights of Rackspace Cloud Block Storage include:

-  Mount a drive to a Cloud Server to scale storage without paying for more compute capability.

-  A high performance option for databases and high performance applications, leveraging solid state drives (SSDs) for speed.

-  A standard speed option using SATA drive for customers who just need additional storage on their Cloud Server.

..  note::
    Cloud Block Storage is an add-on feature to Next Generation Cloud Servers. Customers may not attach Cloud Block Storage volumes to other instances, like first generation Cloud Servers.

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

.. _cbs-dg-audience:

Intended audience
~~~~~~~~~~~~~~~~~

This guide is intended to assist software developers who want to develop applications by using the Rackspace Cloud Block Storage API. It assumes the reader has a general understanding of storage and is familiar with the following items:

-  RESTful web services

-  HTTP/1.1 conventions

-  JSON data serialization formats

.. _cbs-dg-overview-changehist:

Document change history
~~~~~~~~~~~~~~~~~~~~~~~

This version of this guide replaces and obsoletes all earlier versions. The most recent changes are described in the following table:

+----------------+-------------------------------------------------------------------------------------------------+
| Revision Date  |         Summary of Changes                                                                      |
+================+=================================================================================================+
| June 4, 2015   | Updated the "Delete volume" operation description by adding a note that if a snapshot of the    |
|                | volume exists, you cannot delete the volume until you delete the snapshot.                      |
+----------------+-------------------------------------------------------------------------------------------------+
| May 20, 2015   | Corrected the size description to show that size is in gibibytes (GiB) rather than GB in        |
|                | "Create volume".                                                                                |
+----------------+-------------------------------------------------------------------------------------------------+
| April 23, 2015 | Corrected links in "Assigning roles to account users".                                          |
|                |                                                                                                 |
+----------------+-------------------------------------------------------------------------------------------------+

.. _cbs-dg-overview-additional:

Additional resources
~~~~~~~~~~~~~~~~~~~~

You can download the most current versions of the API-related documents from `docs.rackspace.com`_.

For information about Rackspace Cloud products, the `Rackspace Cloud site`_ offers links to the official support channels for Rackspace, including knowledge base articles, forums, phone, chat, and email.

You can follow Rackspace updates and announcements `via twitter`_.

This API uses standard `HTTP 1.1 response codes`_.

.. _docs.rackspace.com: http://docs.rackspace.com/
.. _Rackspace Cloud site: http://www.rackspace.com/cloud/
.. _via twitter: https://twitter.com/rackspace
.. _HTTP 1.1 response codes: http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html

.. _cbs-dg-overview-contract:

API contract changes
~~~~~~~~~~~~~~~~~~~~

Rackspace notifies customers in release notes when and if the contract changes.

.. _cbs-dg-overview-pricing:

Pricing and service level
~~~~~~~~~~~~~~~~~~~~~~~~~

Cloud Block Storage is part of the Rackspace Cloud and your use of the Cloud Block Storage API will be billed according to the `pricing schedule`_.

The Service Level Agreement (SLA) for Cloud Block Storage is available on the `Rackspace Legal Information`_ page.

.. _pricing schedule: http://www.rackspace.com/cloud/block-storage/

.. _Rackspace Legal Information: http://www.rackspace.com/information/legal/cloud/sla?page

.. _cbs-dg-overview-terminology:

Terminology
~~~~~~~~~~~

To use the Cloud Block Storage API effectively, you should understand the terms defined in the :ref:`Glossary <cbs-dg-glossary>`.
