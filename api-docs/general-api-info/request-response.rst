.. _request-response-types:

==========================
Request and response types
==========================

The Cloud Block Storage API supports both the JSON and XML data
serialization formats. 

The request format is specified by using the
``Content-Type`` header and is required for operations that have a request
body. 

The response format can be specified in requests either by using
the ``Accept`` header or by adding an ``.xml`` or ``.json`` extension to
the request URI. A
response  can be serialized using a format that is different from the request.
If no response format is specified, JSON is the default. If conflicting
formats are specified by using both an ``Accept`` header and a query
extension, the query extension takes precedence.

.. list-table:: **JSON and XML response formats**
   :widths: 10 20 10 10
   :header-rows: 1

   * - Format
     - Accept header
     - Query extension
     - Default
   * - JSON
     - application/json
     - .json
     - Yes
   * - XML
     - application/xml
     - .xml
     - No


In the request example below, notice that ``Content-Type`` is set to
``application/json``, but ``application/xml`` is requested via the
``Accept`` header.

**Example: Request with headers (listing volume types)**

.. code::

     GET /v1/441446/types HTTP/1.1
     Host: dfw.blockstorage.api.rackspacecloud.com
     X-Auth-Token: eaaafd18-0fed-4b3a-81b4-663c99ec1cbb
     Content-Type: application/json
     Accept: application/xml

An XML response format is returned.

**Example: XML response with headers**

.. code::

      HTTP/1.1 200 OK
      Date: Fri, 20 Jul 2012 20:32:13 GMT
      Content-Length: 187
      Content-Type: application/xml
      X-Compute-Request-Id: req-8e0295cd-a283-46e4-96da-cae05cbfd1c7

      <?xml version='1.0' encoding='UTF-8'?>
      <volume_types>
          <volume_type id="1" name="SATA">
              <extra_specs/>
          </volume_type>
          <volume_type id="2" name="SSD">
              <extra_specs/>
          </volume_type>
      </volume_types>
