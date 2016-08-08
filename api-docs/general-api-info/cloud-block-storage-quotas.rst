.. _quotas:

==========================
Cloud Block Storage quotas
==========================

All new Cloud Block Storage users are assigned default quotas that limit
the amount of block storage that can be provisioned in each region.
Default quotas enable users to provision up to 10 TB of SATA and 10 TB
of SSD and are primarily used to help with capacity planning and to
prevent system abuse. If your application requires more storage or
volumes than the default quotas, simply submit a support request to ask
for an increase. In your request, be sure to include the following
information:

*  Total storage amount that you need (in GBs or TBs)

*  Storage type (SATA or SSD)

*  Region (for example, DFW or LON)

.. note::

   Cloud Block Storage quotas are independent from any other account quotas
   that you might have. In addition, Cloud Block Storage no longer supports
   account quotas (previously shared by SATA and SSD) or number-of-volumes
   quotas. Both of these quotas were replaced by the storage-type quotas, which
   are specific to SATA and SSD per account per region.

You can use the OpenStack Cinder client or API to see your current block
storage quota and your current utilization against it.

For Cinder client users, use the following command:

.. code::

    $ cinder quota-usage yourAccountID

Your account ID or account number is often referred to as your tenant ID or
tenant name. For information about how to find your account ID, see the
Authentication section.

This results in a quota listing similar to the following example.

**Example: Response showing quota and usage information**

.. code::

     +----------------+--------+----------+-------+
     |      Type      | In_use | Reserved | Limit |
     +----------------+--------+----------+-------+
     |   gigabytes    |  100   |    0     |   -1  |
     | gigabytes_SATA |  100   |    0     | 10240 |
     | gigabytes_SSD  |   0    |    0     | 10240 |
     |   snapshots    |  12    |    0     |   -1  |
     | snapshots_SATA |   1    |    0     |   -1  |
     | snapshots_SSD  |   0    |    0     |   -1  |
     |    volumes     |   1    |    0     |   -1  |
     |  volumes_SATA  |   1    |    0     |   -1  |
     |  volumes_SSD   |   0    |    0     |   -1  |
     +----------------+--------+----------+-------+

The following table describes the information in the quota listing.

**Table: Cloud Block Storage quota properties**

+---------------+-------------------------------------------------------------+
| Property name | Value description                                           |
+===============+=============================================================+
| gigabytes     | Volume gigabytes allowed for each tenant. Gigabytes for     |
|               | SATA and SSD are given.                                     |
+---------------+-------------------------------------------------------------+
| snapshots     | Volume snapshots allowed for each tenant. Snapshots for     |
|               | SATA and SSD are given.                                     |
+---------------+-------------------------------------------------------------+
| volumes       | Volumes allowed for each tenant. Volumes for SATA and SSD   |
|               | are given.                                                  |
+---------------+-------------------------------------------------------------+

To use the Cinder API, you can use a cURL request similar to the
following example to see your current block storage quota and your
current activity against it. If you use the ``usage=True`` query
parameter, the response includes the usage information. If you do not
include the query parameter, the response includes only quota information.

**Example: cURL request to show quota and usage information**

.. code::

    curl -i -X GET https://dfw.blockstorage.api.rackspacecloud.com/v1/yourAccountID/os-quota-sets/yourAccountID?usage=True \
    -H "X-Auth-Project-Id: yourAccountID" \
    -H "User-Agent: python-cinderclient" \
    -H "Accept: application/json" \
    -H "X-Auth-Token: yourAuthToken"

**Example: Response from the cURL request to show quota and usage information**

.. code::

    {
        "quota_set": {
            "gigabytes": {
                "in_use": 100,
                "limit": -1,
                "reserved": 0
            },
            "gigabytes_SATA": {
                "in_use": 100,
                "limit": 10240,
                "reserved": 0
            },
            "gigabytes_SSD": {
                "in_use": 0,
                "limit": 10240,
                "reserved": 0
            },
            "id": "yourAccountID",
            "snapshots": {
                "in_use": 12,
                "limit": -1,
                "reserved": 0
            },
            "snapshots_SATA": {
                "in_use": 1,
                "limit": -1,
                "reserved": 0
            },
            "snapshots_SSD": {
                "in_use": 0,
                "limit": -1,
                "reserved": 0
            },
            "volumes": {
                "in_use": 1,
                "limit": -1,
                "reserved": 0
            },
            "volumes_SATA": {
                "in_use": 1,
                "limit": -1,
                "reserved": 0
            },
            "volumes_SSD": {
                "in_use": 0,
                "limit": -1,
                "reserved": 0
            }
        }
    }
