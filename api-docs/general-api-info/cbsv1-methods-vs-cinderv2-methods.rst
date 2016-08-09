.. _cbs-methods-vs-cinder-methods:

===================================================================================================
Differences between Rackspace Cloud Block Storage v1 methods and OpenStack Block Storage v2 methods
===================================================================================================

Rackspace Cloud Block Storage v1 (referred to as Cloud Block Storage in the
rest of this section) can run the corresponding OpenStack Block Storage v2
(referred to as Cinder in the rest of this section) methods. However,
differences exist between the them.

The following table provides the differences by method.

**Table: Differences between Cloud Block Storage v1 methods and Cinder v2 methods**

+-----------------------------+-------------------------------------------------------+
| Method name                 | Difference                                            |
+=============================+=======================================================+
| Create volume               | The Cloud Block Storage normal response code is 200,  |
|                             | but the Cinder code is 202.                           |
|                             |                                                       |
|                             | Cloud Block Storage includes information about how to |
|                             | use ``metadata`` to create volumes on different nodes |
|                             | or racks than existing volumes (disaffinity).         |
|                             |                                                       |
|                             | The Cloud Block Storage request and response body     |
|                             | parameters have the following differences from Cinder:|
|                             |                                                       |
|                             | - ``display_description`` rather than ``description`` |
|                             |                                                       |
|                             | - ``display_name`` rather than ``name``               |
|                             |                                                       |
|                             | Cloud Block Storage does not include the following    |
|                             | request parameters (which Cinder includes):           |
|                             |                                                       |
|                             | - ``consistencygroup_id``                             |
|                             |                                                       |
|                             | - ``multiattach``                                     |
|                             |                                                       |
|                             | - ``scheduler_hints``                                 |
|                             |                                                       |
|                             | - ``source_replica``                                  |
|                             |                                                       |
|                             | The Cloud Block Storage response does not include the |
|                             | following response parameters:                        |
|                             |                                                       |
|                             | - ``migration_status``                                |
|                             |                                                       |
|                             | - ``user_id``                                         |
|                             |                                                       |
|                             | - ``links``                                           |
|                             |                                                       |
|                             | - ``encrypted``                                       |
|                             |                                                       |
|                             | - ``updated_at``                                      |
|                             |                                                       |
|                             | - ``replication_status``                              |
|                             |                                                       |
|                             | - ``consistencygroup_id``                             |
|                             |                                                       |
|                             | - ``encrypted``                                       |
|                             |                                                       |
|                             | - ``multiattach``                                     |
|                             |                                                       |
|                             | - ``replication_status``                              |
|                             |                                                       |
|                             | - ``consistencygroup_id``                             |
+-----------------------------+-------------------------------------------------------+
| List volumes                | Cloud Block Storage does not include the following    |
|                             | query parameters (which Cinder includes):             |
|                             |                                                       |
|                             | - ``sort``                                            |
|                             |                                                       |
|                             | - ``limit``                                           |
|                             |                                                       |
|                             | - ``marker``                                          |
|                             |                                                       |
|                             | The Cloud Block Storage response body parameters have |
|                             | the following differences from Cinder:                |
|                             |                                                       |
|                             | - ``display_name`` rather than ``name``               |
|                             |                                                       |
|                             | The Cloud Block Storage includes the following        |
|                             | response parameters that Cinder does not include:     |
|                             |                                                       |
|                             | - ``display_description``                             |
|                             |                                                       |
|                             | - ``size``                                            |
|                             |                                                       |
|                             | - ``volume_type``                                     |
|                             |                                                       |
|                             | - ``snapshot_id``                                     |
|                             |                                                       |
|                             | - ``attachments``                                     |
|                             |                                                       |
|                             | The Cloud Block Storage does not includes the         |
|                             | following response parameters that Cinder does        |
|                             | include:                                              |
|                             |                                                       |
|                             | - ``links`` with ``href`` and ``rel``                 |
+-----------------------------+-------------------------------------------------------+
| List volumes(detailed)      | Cloud Block Storage does not include the following    |
|                             | query parameters (which Cinder includes):             |
|                             |                                                       |
|                             | - ``sort``                                            |
|                             |                                                       |
|                             | - ``limit``                                           |
|                             |                                                       |
|                             | - ``marker``                                          |
|                             |                                                       |
|                             | The Cloud Block Storage response body parameters have |
|                             | the following differences from Cinder:                |
|                             |                                                       |
|                             | - ``display_description`` rather than ``description`` |
|                             |                                                       |
|                             | - ``display_name`` rather than ``name``               |
|                             |                                                       |
|                             | The Cloud Block Storage response does not include the |
|                             | following response parameters:                        |
|                             |                                                       |
|                             | - those that are prefixed with``os-``                 |
|                             |                                                       |
|                             | - ``encrypted``                                       |
|                             |                                                       |
|                             | - ``multiattach``                                     |
|                             |                                                       |
|                             | - ``consistencygroup_id``                             |
|                             |                                                       |
|                             | - ``migration-status``                                |
|                             |                                                       |
|                             | - ``updated_at``                                      |
|                             |                                                       |
|                             | - ``replication_status``                              |
|                             |                                                       |
|                             | - ``user_id``                                         |
|                             |                                                       |
|                             | - ``bootable``                                        |
+-----------------------------+-------------------------------------------------------+
| Show volume                 | The Cloud Block Storage response parameters have the  |
|                             | following differences from Cinder:                    |
|                             |                                                       |
|                             | - ``display_name`` rather than ``name``               |
|                             |                                                       |
|                             | The Cloud Block Storage response does not include the |
|                             | following response parameters:                        |
|                             |                                                       |
|                             | - those that are prefixed with``os-``                 |
|                             |                                                       |
|                             | - ``encrypted``                                       |
|                             |                                                       |
|                             | - ``multiattach``                                     |
|                             |                                                       |
|                             | - ``consistencygroup_id``                             |
|                             |                                                       |
|                             | - ``migration-status``                                |
|                             |                                                       |
|                             | - ``links``                                           |
|                             |                                                       |
|                             | - ``updated_at``                                      |
|                             |                                                       |
|                             | - ``replication_status``                              |
|                             |                                                       |
|                             | - ``user_id``                                         |
|                             |                                                       |
|                             | - ``description``                                     |
+-----------------------------+-------------------------------------------------------+
| Update volume               | The Cloud Block Storage request parameters have the   |
|                             | following differences from Cinder:                    |
|                             |                                                       |
|                             | - ``display_description`` rather than ``description`` |
|                             |                                                       |
|                             | - ``display_name`` rather than ``name``               |
|                             |                                                       |
|                             | - excludes ``metadata``                               |
|                             |                                                       |
|                             | The Cloud Block Storage response parameters have the  |
|                             | following differences from Cinder:                    |
|                             |                                                       |
|                             | - ``display_description`` rather than ``description`` |
|                             |                                                       |
|                             | - ``display_name`` rather than ``name``               |
|                             |                                                       |
|                             | The Cloud Block Storage response does not include the |
|                             | following response parameters:                        |
|                             |                                                       |
|                             | - ``encrypted``                                       |
|                             |                                                       |
|                             | - ``multiattach``                                     |
|                             |                                                       |
|                             | - ``consistencygroup_id``                             |
|                             |                                                       |
|                             | - ``migration-status``                                |
|                             |                                                       |
|                             | - ``links``                                           |
|                             |                                                       |
|                             | - ``updated_at``                                      |
|                             |                                                       |
|                             | - ``replication_status``                              |
|                             |                                                       |
|                             | - ``user_id``                                         |
|                             |                                                       |
|                             | - ``description``                                     |
+-----------------------------+-------------------------------------------------------+
| Delete volume               | No differences.                                       |
+-----------------------------+-------------------------------------------------------+
| List volume types           | Cloud Block Storage does not include the following    |
|                             | query parameters (which Cinder includes):             |
|                             |                                                       |
|                             | - ``sort_key``                                        |
|                             |                                                       |
|                             | - ``sort_dir``                                        |
|                             |                                                       |
|                             | - ``limit``                                           |
|                             |                                                       |
|                             | - ``marker``                                          |
+-----------------------------+-------------------------------------------------------+
| List volume type (detailed) | The Cloud Block Storage response does not include the |
|                             | following response parameters:                        |
|                             |                                                       |
|                             | - ``description``                                     |
|                             |                                                       |
|                             | - ``is_public``                                       |
+-----------------------------+-------------------------------------------------------+
| Create snapshot             | The Cloud Block Storage successful response code is   |
|                             | 201, but the Cinder code is 202.                      |
|                             |                                                       |
|                             | The Cloud Block Storage request and response body     |
|                             | parameters have the following differences from Cinder:|
|                             |                                                       |
|                             | - ``display_description`` rather than ``description`` |
|                             |                                                       |
|                             | - ``display_name`` rather than ``name``               |
|                             |                                                       |
|                             | The Cloud Block Storage response includes the         |
|                             | following response parameters that Cinder does not    |
|                             | include:                                              |
|                             |                                                       |
|                             | - ``os-extended-snapshot-attributes:progress``        |
|                             |                                                       |
|                             | - ``os-extended-snapshot-attributes:project_id``      |
|                             |                                                       |
+-----------------------------+-------------------------------------------------------+
| List snapshots              | Cloud Block Storage does not include the following    |
|                             | query parameters (which Cinder includes):             |
|                             |                                                       |
|                             | - ``sort_key``                                        |
|                             |                                                       |
|                             | - ``sort_dir``                                        |
|                             |                                                       |
|                             | - ``limit``                                           |
|                             |                                                       |
|                             | - ``marker``                                          |
|                             |                                                       |
|                             | The Cloud Block Storage response body parameters have |
|                             | the following differences from Cinder:                |
|                             |                                                       |
|                             | - ``display_description`` rather than ``description`` |
|                             |                                                       |
|                             | - ``display_name`` rather than ``name``               |
|                             |                                                       |
|                             | The Cloud Block Storage response does not include the |
|                             | following response parameter:                         |
|                             |                                                       |
|                             | - ``metadata``                                        |
+-----------------------------+-------------------------------------------------------+
| List snapshots (detailed)   | The Cloud Block Storage response body parameters have |
|                             | the following differences from Cinder:                |
|                             |                                                       |
|                             | - ``display_description`` rather than ``description`` |
|                             |                                                       |
|                             | - ``display_name`` rather than ``name``               |
+-----------------------------+-------------------------------------------------------+
| Show snapshot details       | The Cloud Block Storage response body parameters have |
|                             | the following differences from Cinder:                |
|                             |                                                       |
|                             | - ``display_description`` rather than ``description`` |
|                             |                                                       |
|                             | - ``display_name`` rather than ``name``               |
+-----------------------------+-------------------------------------------------------+
| Update snapshot             | The Cloud Block Storage request body parameters have  |
|                             | the following differences from Cinder:                |
|                             |                                                       |
|                             | - ``display_description`` rather than ``description`` |
|                             |                                                       |
|                             | - ``display_name`` rather than ``name``               |
|                             |                                                       |
|                             | The Cloud Block Storage response does not include the |
|                             | following response parameter:                         |
|                             |                                                       |
|                             | - ``metadata``                                        |
+-----------------------------+-------------------------------------------------------+
| Delete snapshot             | No differences.                                       |
+-----------------------------+-------------------------------------------------------+
| Show snapshot metadata      | The Cloud Block Storage response body parameters have |
|                             | the following differences from Cinder:                |
|                             |                                                       |
|                             | - ``display_description`` rather than ``description`` |
|                             |                                                       |
|                             | - ``display_name`` rather than ``name``               |
+-----------------------------+-------------------------------------------------------+

Cinder v2 returns the following statuses for volume operations, which Cloud
Block Storage v1 does not include: 

- Backing-up
- Restoring-backup
- Error-restoring
- Error-extending

For Cloud Block Storage v1 statuses, see :ref:`Volumes <volumes-operations>`.
