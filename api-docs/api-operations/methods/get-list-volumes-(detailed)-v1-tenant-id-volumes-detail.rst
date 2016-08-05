.. _get-list-volumes-detail:

Retrieve volumes (detailed)
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

    GET /v1/{tenant_id}/volumes/detail

This operation retrieves detailed information for all Cloud Block Storage
volumes that the tenant who submits the request can access.

Request
-------

The request has the following URI parameters.

+--------------------------+-------------------------+------------------------+
|Name                      |Type                     |Description             |
+==========================+=========================+========================+
|{tenant_id}               |String                   |The unique identifier of|
|                          |                         |the tenant or account.  |
+--------------------------+-------------------------+------------------------+

This operation does not accept a request body.

Response examples
-----------------

The following example shows the XML response for retrieving the volume details.

.. code::

   <?xml version='1.0' encoding='UTF-8'?>
   <volumes xmlns="http://docs.rackspace.com/volume/api/v1">
       <volume xmlns="http://docs.rackspace.com/volume/api/v1"
           status="available" name="vol-004" availability_zone="nova"
           created_at="2013-02-25 06:36:28" description="Another volume."
           volume_type="None" source_volid="None" snapshot_id="None"
           id="45baf976-c20a-4894-a7c3-c94b7376bf55" size="1"
           tenant_id="0c2eba2c5af04d3f9e9d0d410b371fde"
           host="ip-10-168-107-25">
           <attachments/>
           <metadata>
               <meta key="contents">junk</meta>
           </metadata>
       </volume>
       <volume status="available" name="vol-003" availability_zone="nova"
           created_at="2013-02-25 02:40:21"
           description="This is yet, another volume." volume_type="None"
           source_volid="None" snapshot_id="None"
           id="5aa119a8-d25b-45a7-8d1b-88e127885635" size="1"
           tenant_id="0c2eba2c5af04d3f9e9d0d410b371fde"
           host="ip-10-168-107-25">
           <attachments/>
           <metadata>
               <meta key="contents">not junk</meta>
           </metadata>
       </volume>
   </volumes>

The following example shows the JSON response for retrieving the volume
details.

.. code::

   {
       "volumes": [
           {
               "id": "521752a6-acf6-4b2d-bc7a-119f9148cd8c",
               "display_name": "vol-001",
               "display_description": "Another volume.",
               "size": 100,
               "volume_type": "SATA",
               "snapshot_id": null,
               "attachments": [],
               "created_at": "2012-02-14T20:53:07Z"
           },
           {
               "id": "76b8950a-8594-4e5b-8dce-0dfa9c696358",
               "display_name": "vol-002",
               "display_description": "Yet another volume.",
               "size": 100,
               "volume_type": "SATA",
               "snapshot_id": null,
               "attachments": [],
               "created_at": "2012-03-15T19:10:03Z"
           }
       ]
   }

   {
       "volumes":[
          {
             "status":"available",
             "attachments":[

             ],
             "links":[
                {
                   "href":"http://localhost:8776/v2/0c2eba2c5af04d3f9e9d0d410b371fde/volumes/45baf976-c20a-4894-a7c3-c94b7376bf55",
                   "rel":"self"
                },
                {
                   "href":"http://localhost:8776/0c2eba2c5af04d3f9e9d0d410b371fde/volumes/45baf976-c20a-4894-a7c3-c94b7376bf55",
                   "rel":"bookmark"
                }
                  ],
                  "availability_zone":"nova",
                  "host":"ip-10-168-107-25",
                  "source_volid":null,
                  "snapshot_id":null,
                  "id":"45baf976-c20a-4894-a7c3-c94b7376bf55",
                  "description":"Another volume.",
                  "name":"vol-004",
                  "created_at":"2013-02-25T06:36:28.000000",
                  "volume_type":"None",
                  "tenant_id":"0c2eba2c5af04d3f9e9d0d410b371fde",
                  "size":1,
                  "metadata":{
                  "contents":"junk"
                  }
               },
               {
                  "status":"available",
                  "attachments":[

                  ],
                  "links":[
                   {
                       "href":"http://localhost:8776/v2/0c2eba2c5af04d3f9e9d0d410b371fde/volumes/5aa119a8-d25b-45a7-8d1b-88e127885635",
                       "rel":"self"
                   },
                   {
                       "href":"http://localhost:8776/0c2eba2c5af04d3f9e9d0d410b371fde/volumes/5aa119a8-d25b-45a7-8d1b-88e127885635",
                       "rel":"bookmark"
                   }
               ],
               "availability_zone":"nova",
               "host":"ip-10-168-107-25",
               "source_volid":null,
               "snapshot_id":null,
               "id":"5aa119a8-d25b-45a7-8d1b-88e127885635",
               "description":"This is yet, another volume.",
               "name":"vol-003",
               "created_at":"2013-02-25T02:40:21.000000",
               "volume_type":"None",
               "tenant_id":"0c2eba2c5af04d3f9e9d0d410b371fde",
               "size":1,
               "metadata":{
               "contents":"not junk"
               }
           }
       ]
   }

Response codes
--------------

+--------------------------+-------------------------+------------------------+
|Response Code             |Name                     |Description             |
+==========================+=========================+========================+
|200                       |OK                       |Success                 |
+--------------------------+-------------------------+------------------------+
