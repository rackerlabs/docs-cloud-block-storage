.. _paginated-collections:

=====================
Paginated collections
=====================

.. COMMENT: This section has been adapted from the template file to have
   information specific to Cloud Block Storage.

To reduce load on the service, retrieve operations return a maximum limit of
1000 items at a time by default. If a request supplies no limit or one that
exceeds the configured default limit, the default limit is used instead.

This behavior is called *pagination*. Pagination gives you the ability to
limit the size of the returned data and to retrieve a specified subset of a
large data set. Pagination is handled by two parameters in Cloud Block Storage:
limit and offset.

* *Limit* is the restriction on the maximum number of items that are returned.

* *Offset* is a count of the number of objects from where the paginated list
  is started.

To navigate the collection, you can set the ``limit`` and ``offset``
parameters in the URI. For example, ``?limit=100&offset=10`` displays a
maximum of 100 items from the retrieve operation in the paginated results with
an offset of 10 items.
