Group API Procedures
====================

POST: group/group
-----------

-  Purpose: **Create a new group**
-  Parameters:

   -  **name** (string, required)
   -  **external_id** (string, optional)

-  Result on success: **link_id**
-  Result on failure: **false**

Request example:

.. code:: json

     [  "My Group B",
            "1234"  ]

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1416806551,
        "result": 2
    }

PUT: group/group
-----------

-  Purpose: **Update a group**
-  Parameters:

   -  **group_id** (integer, required)
   -  **name** (string, optional)
   -  **external_id** (string, optional)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json
 
   { "group_id": "1",
     "name": "ABC",
     "external_id": "something" }

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 866078030,
        "result": true
    }

DELTE: group/group
-----------

-  Purpose: **Remove a group**
-  Parameters:

   -  **group_id** (integer, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

     [ "1"  ]

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 566000661,
        "result": true
    }

GET: group/group
--------

-  Purpose: **Get one group**
-  Parameters:

   -  **group_id** (integer, required)

-  Result on success: **Group dictionary**
-  Result on failure: **false**

Request example:

.. code:: json

     [ "1" ]

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1968647622,
        "result": {
            "id": "1",
            "external_id": "",
            "name": "My Group A"
        }
    }

GET: group/allgroups
------------

-  Purpose: **Get all groups**
-  Parameters: none
-  Result on success: **list of groups**
-  Result on failure: **false**

Request example:

.. code:: json


Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 546070742,
        "result": [
            {
                "id": "1",
                "external_id": "",
                "name": "My Group A"
            },
            {
                "id": "2",
                "external_id": "1234",
                "name": "My Group B"
            }
        ]
    }
