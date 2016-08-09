.. _response-codes:

==============
Response codes
==============

Cloud Block Storage returns an HTTP code that denotes the type of response.

-  Successful response codes are returned only if all configured
   providers were successful in processing the request.

-  Error response codes are accompanied by an ``application/xml`` or
   ``application/json`` response body that contains the error messages.

This API uses `standard HTTP 1.1 response codes`_.

The following table lists possible responses with their associated codes
and descriptions.

**Table: Response codes**

+---------------------+-----------------------+-------------------------------+
| Response            | Associated response   | Description                   |
|                     | code                  |                               |
+=====================+=======================+===============================+
| OK                  | 200                   | The request has               |
|                     |                       | succeeded.                    |
|                     |                       | (Some API calls               |
|                     |                       | return 201 instead.)          |
+---------------------+-----------------------+-------------------------------+
| Created             | 201                   | The request has been          |
|                     |                       | fulfilled and a               |
|                     |                       | resource was created.         |
+---------------------+-----------------------+-------------------------------+
| Accepted            | 202                   | The request has been          |
|                     |                       | accepted for                  |
|                     |                       | processing.                   |
+---------------------+-----------------------+-------------------------------+
| No Content          | 204                   | The request has been          |
|                     |                       | fulfilled but does not        |
|                     |                       | return a                      |
|                     |                       | representation (that          |
|                     |                       | is, the response is           |
|                     |                       | empty).                       |
+---------------------+-----------------------+-------------------------------+
| badRequest          | 400                   | There was one or more errors  |
|                     |                       | in the user request.          |
+---------------------+-----------------------+-------------------------------+
| unauthorized        | 401                   | The supplied token is not     |
|                     |                       | authorized to access the      |
|                     |                       | resources, either it's        |
|                     |                       | expired or invalid.           |
+---------------------+-----------------------+-------------------------------+
| forbidden           | 403                   | Access to the requested       |
|                     |                       | resource was denied.          |
+---------------------+-----------------------+-------------------------------+
| itemNotFound        | 404                   | The back-end services did not |
|                     |                       | find anything matching the    |
|                     |                       | Request-URI.                  |
+---------------------+-----------------------+-------------------------------+
| badMethod           | 405                   | The requested method is not   |
|                     |                       | allowed for this resource.    |
+---------------------+-----------------------+-------------------------------+
| invalidImage        | 412                   | This fault is related to      |
|                     |                       | creating volumes for the boot |
|                     |                       | from volume feature. The      |
|                     |                       | uncompressed image size must  |
|                     |                       | be 127 GB or less.            |
+---------------------+-----------------------+-------------------------------+
| overLimit           | 413                   | Either the number of entities |
|                     |                       | in the request is larger than |
|                     |                       | allowed limits, or the user   |
|                     |                       | has exceeded allowable        |
|                     |                       | request rate limits. See the  |
|                     |                       | details element for more      |
|                     |                       | specifics. Contact support if |
|                     |                       | you think you need higher     |
|                     |                       | request rate limits.          |
+---------------------+-----------------------+-------------------------------+
| badMediaType        | 415                   | The requested content type is |
|                     |                       | not supported by this service |
+---------------------+-----------------------+-------------------------------+
| unprocessableEntity | 422                   | The requested resource could  |
|                     |                       | not be processed on at the    |
|                     |                       | moment.                       |
+---------------------+-----------------------+-------------------------------+
| instanceFault       | 500                   | This is a generic server error|
|                     |                       | and the message contains the  |
|                     |                       | reason for the error. This    |
|                     |                       | error could wrap several error|
|                     |                       | messages and is a catch all.  |
+---------------------+-----------------------+-------------------------------+
| notImplemented      | 501                   | The requested method or       |
|                     |                       | resource is not implemented.  |
+---------------------+-----------------------+-------------------------------+
| serviceUnavailable  | 503                   | The Cloud Block Storage       |
|                     |                       | service is not available.     |
+---------------------+-----------------------+-------------------------------+

The following ``instanceFault`` examples show errors when the server has
erred or cannot perform the requested operation.

**Example: instanceFault response in XML**

.. code::

    HTTP/1.1 500 Internal Server Error
    Content-Type: application/xml
    Content-Length: 121
    Date: Mon, 28 Nov 2011 18:19:37 GMT

.. code::

    <?xml version="1.0" encoding="UTF-8"?>
    <instanceFault code="500"
        xmlns="http://docs.rackspace.com/cbs/api/v1.0">
        <message> The server has either erred or is incapable of
            performing the requested operation. </message>
    </instanceFault>


**Example: fault response in JSON**

.. code::

    HTTP/1.1 500 Internal Server Error
    Content-Length: 120
    Content-Type: application/json; charset=UTF-8
    Date: Tue, 29 Nov 2011 00:33:48 GMT

.. code::

    {
       "instance_fault":{
          "code":500,
          "message":"The server has either erred or is incapable of performing the requested operation."
       }
    }

The error code (``code``) is returned in the body of the response for
convenience. The ``message`` element returns a human-readable message
that is appropriate for display to the end user. The ``details`` element
is optional and may contain information that is useful for tracking down
an error, such as a stack trace. The ``details`` element may or may not
be appropriate for display to an end user, depending on the role and
experience of the end user.

The root element of the fault (for example, ``instanceFault``) may
change depending on the type of error.

The following ``badRequest`` examples show errors when the volume size
is invalid.

**Example: badRequest fault on volume size errors in XML**

.. code::

    HTTP/1.1 400 None
    Content-Type: application/xml
    Content-Length: 121
    Date: Mon, 28 Nov 2011 18:19:37 GMT

.. code::

    <?xml version="1.0" encoding="UTF-8"?>
    <badRequest code="400" xmlns="http://docs.rackspace.com/cbs/api/v1.0">
        <message> Volume 'size' needs to be a positive integer value, -1.0
            cannot be accepted. </message>
    </badRequest>

**Example: badRequest fault on volume size errors in JSON**

.. code::

    HTTP/1.1 400 None
    Content-Length: 120
    Content-Type: application/json; charset=UTF-8
    Date: Tue, 29 Nov 2011 00:33:48 GMT

.. code::

    {
       "badRequest":{
          "code":400,
          "message":"Volume 'size' needs to be a positive integer value, -1.0 cannot be accepted."
       }
    }

The next examples show ``itemNotFound`` errors.

**Example: itemNotFound fault in XML**

.. code::

    HTTP/1.1 404 Not Found
    Content-Length: 147
    Content-Type: application/xml; charset=UTF-8
    Date: Mon, 28 Nov 2011 19:50:15 GMT

.. code::

    <?xml version="1.0" encoding="UTF-8"?>
    <itemNotFound code="404"
        xmlns="http://docs.rackspace.com/cbs/api/v1.0">
        <message> The resource could not be found. </message>
    </itemNotFound>

**Example: itemNotFound fault in JSON**

.. code::

    HTTP/1.1 404 Not Found
    Content-Length: 78
    Content-Type: application/json; charset=UTF-8
    Date: Tue, 29 Nov 2011 00:35:24 GMT

.. code::

    {
        "item_not_found": {
            "code": 404,
            "message": "The resource could not be found."
        }
    }

.. _standard HTTP 1.1 response codes: http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html