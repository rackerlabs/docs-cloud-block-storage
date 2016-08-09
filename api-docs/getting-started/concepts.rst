.. _concepts:

==================
|service| concepts
==================

To use the Cloud Block Storage API effectively, you should understand
the following terms:

Instance
~~~~~~~~

An instance is a virtual machine that runs inside the cloud.

Instance type
~~~~~~~~~~~~~

An instance type describes the compute, memory, and storage capacity of Nova
computing instances. In layman's terms, this is the size (in terms of vCPUs,
RAM, and so forth) of the virtual server that you will be launching.

Snapshot
~~~~~~~~

A snapshot is a point-in-time copy of the data contained in a volume.

Volume
~~~~~~

A volume is a detachable block storage device. You can think of it as a USB
hard drive. It can only be attached to one instance at a time.

Volume type
~~~~~~~~~~~

The volume type is the type of a block storage volume. There are two types:
SATA for standard performance and SSD for high performance.
