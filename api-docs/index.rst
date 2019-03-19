.. _index:

===============================================
|product name| API |contract version|
===============================================

*Last updated:* |today|

Rackspace Cloud Block Storage enables customers to mount drives or volumes to
their Rackspace Next Generation Cloud Servers™ and OnMetal™ Cloud Servers. The
primary use cases for Cloud Block Storage are to enable you to perform the
following tasks:

-  Scale your storage independently from your compute resources.

-  Use high performance storage to serve database or I/O-intensive
   applications.

Rackspace Cloud Block Storage provides the following offerings:

-  The ability to mount a drive to a Cloud Server to scale storage without
   paying for more compute capability.

-  A standard speed option at a low cost/gigabyte (GB) using SATA drives for
   customers who just need additional storage on their Cloud Server.

-  A high performance option for databases and high performance applications,
   leveraging solid state drives (SSDs) for speed (at a higher cost/GB).

..  note::
    Cloud Block Storage is an add-on feature to Next Generation Cloud Servers
    and OnMetal Cloud Servers. Customers can not attach Cloud Block Storage
    volumes to other instances, like first generation Cloud Servers.

    Cloud Block Storage is a multi-tenant rather than a dedicated service.

    When volumes are destroyed, Rackspace keeps that disk space unavailable
    until zeros have been written to the space to ensure that data is not
    accessible by any other customers.

    Cloud Block Storage allows you to create snapshots that you can save, list,
    and restore.

Cloud Block Storage is built on the OpenStack Cinder project. For more
information about OpenStack Cinder, see the
`OpenStack Block Storage API v1 Reference`_.

This guide is intended to assist software developers who want to develop
applications by using the REST application programming interface (API) for
the |product name| service.

To use the information provided here, you should have a general understanding
of the service and have access to an installation of it. You should also be
familiar with the following technologies:

* RESTful web services
* HTTP/1.1
* JSON or XML serialization formats

Use the following links to go directly to user and reference information for
using the |apiservice|:

- :ref:`Getting started <getting-started-guide>`
- :ref:`General API information <general-api-info>`
- :ref:`API reference <api-reference>`
- :ref:`Release notes <release-notes-collection>`

.. note::

   You can also use |product name| from the Cloud Control Panel.

.. toctree::
   :hidden:
   :maxdepth: 3

   Cloud Block Storage 1.0 <self>
   getting-started/index
   general-api-info/index
   api-reference/index
   release-notes/index
   service-updates
   additional-resources
   copyright

.. _OpenStack Block Storage API v1 Reference: http://developer.openstack.org/api-ref-blockstorage-v1.html
