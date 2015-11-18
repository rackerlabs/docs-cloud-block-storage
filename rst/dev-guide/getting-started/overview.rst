.. _gsg-overview:

Overview 
-----------------------

Rackspace Cloud Block Storage is a block-level storage solution that
enables you to mount drives or volumes to your Next Generation Cloud
Servers™ and OnMetal™ Cloud Servers. The primary use cases for Cloud
Block Storage are to allow you to perform the following tasks:

-  Scale your storage independently from your compute resources.

-  Use high-performance storage to serve database or I/O-intensive
   applications.

The following options are available for mounting drives or volumes to
your server:

-  The standard-performance option offers extra storage capacity with
   mountable SATA drives.

-  The high-performance option offers high speed solid state drives
   (SSDs) for memory-intensive applications.

Cloud Block Storage includes the following functionality:

-  Cloud Block Storage is an add-on feature to Next Generation Cloud
   Servers and OnMetal Cloud Servers. You cannot attach Cloud Block
   Storage volumes to other instances, such as First Generation Cloud
   Servers.

-  Cloud Block Storage is multi-tenant rather than dedicated.

-  When volumes are destroyed, Rackspace keeps that disk space
   unavailable until zeros have been written to the space to ensure that
   data is not accessible by any other customers.

-  Cloud Block Storage enables you to create snapshots that you can
   save, list, and restore.

This guide provides step-by-step instructions for entering the necessary
URLs or commands to use the Cloud Block Storage API. You can find
additional details about Cloud Block Storage in the Cloud Block Storage
Developer Guide at `docs.rackspace.com <http://docs.rackspace.com/>`__.

For more details about the Cloud Block Storage service, see the
information at
`www.rackspace.com <http://www.rackspace.com/cloud/block-storage/>`__
and the Knowledge Center article `Cloud Block Storage
Overview <http://www.rackspace.com/knowledge_center/article/cloud-block-storage-overview>`__.

Rackspace welcomes feedback, comments, and bug reports at
support@rackspacecloud.com.

..  note:: 
    Cloud Block Storage is built on the OpenStack Cinder project. For more
    information about OpenStack Cinder, see the `OpenStack Block Storage API
    v1 Reference <http://docs.openstack.org/api/openstack-block-storage/1.0/content/>`__.
