.. _volumes-operations-v2:

Volumes
~~~~~~~  
   
A volume is a detachable block storage device. You can think of it as a USB hard drive. You can attach a volume to one instance at a time.

The ``snapshot_id`` and ``source_volid`` parameters specify the ID of the snapshot or volume from which this volume originates. If the volume was not created from a snapshot or source volume, these values are null. 

When you make an API call to create, list, or delete volumes, the following volume status values are possible:

* CREATING: The snapshot is being created.

* AVAILABLE: The snapshot is ready for use.

* ATTACHING: The volume is attaching to an instance.

* IN-USE: The volume is attached to an instance.

* DELETING: The snapshot is being deleted.

* ERROR: An error occurred during snapshot creation.

* ERROR_DELETING: An error occurred during snapshot deletion.

* BACKING-UP: The volume is being backed up.

* RESTORING-BACKUP: A backup is being restored to the volume.

* ERROR-RESTORING: A backup restoration error occurred.

* ERROR_EXTENDING: An error occurred while attempting to extend a volume.


   
.. include:: methods-v2/post-create-volume-v2.rst
.. include:: methods-v2/get-list-volumes-v2.rst
.. include:: methods-v2/get-list-volumes-(detailed)-v2.rst
.. include:: methods-v2/get-show-volume-v2.rst
.. include:: methods-v2/put-update-volume-v2.rst
.. include:: methods-v2/delete-volume-v2.rst
