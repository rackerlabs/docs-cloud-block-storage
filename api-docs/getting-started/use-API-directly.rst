.. _gsg-use-API-directly:

=======================================
Create and manage volumes and snapshots
=======================================

You can use the examples in this section to create and manage volumes and
snapshots by using Cloud Block Storage API operations. Example requests are
provided in cURL, followed by the response.

Before running the examples, review the
:ref:`Cloud Block Storage concepts<concepts>`.

For more information about all Cloud Block Storage operations, see the
:ref:`API reference <api-reference>`.

.. note::
     These examples use the ``$API_ENDPOINT``, ``$AUTH_TOKEN``, and
     ``$TENANT_ID`` environment variables to specify the API endpoint,
     authentication token, and project ID values for accessing the service.
     Be sure to :ref:`configure these
     variables<configure-environment-variables>` before running the
     code samples.

.. include:: examples/create-volume.rst
.. include:: examples/list-volumes.rst
.. include:: examples/show-volume-details.rst
.. include:: examples/update-volume.rst
.. include:: examples/delete-volume.rst
.. include:: examples/create-snapshot.rst
.. include:: examples/list-snapshots.rst
.. include:: examples/show-snapshot-details.rst
.. include:: examples/update-snapshot.rst
.. include:: examples/delete-snapshot.rst
.. include:: examples/other-curl-commands.rst
