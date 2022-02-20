Task Metadata API Procedures
============================

GET: taskmetadata/taskmetadata/:id
---------------

-  Purpose: **Get all metadata related to a task by task unique id**
-  Parameters:

   -  **task_id** (integer, required)

-  Result on success: **list of metadata**
-  Result on failure: **empty array**

Request example to fetch all the metada of a task:

.. code:: json


Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 133280317,
        "result": [
            {
                "metaKey1": "metaValue1",
                "metaKey2": "metaValue2"
            }
        ]
    }

GET: taskmetadata/taskmetadatabyname
---------------------

-  Purpose: **Get metadata related to a task by task unique id and
   metakey (name)**
-  Parameters:

   -  **task_id** (integer, required)
   -  **name** (string, required)

-  Result on success: **metadata value**
-  Result on failure: **empty string**

Request example to fetch metada of a task by name:

.. code:: json

     [ 1,
      "metaKey1" ]
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 133280317,
        "result": "metaValue1"
    }

POST: taskmetadata/taskmetadata
----------------

-  Purpose: **Save/update task metadata**
-  Parameters:

   -  **task_id** (integer, required)
   -  **values** (array, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example to add/update metada of a task:

.. code:: json

     [ 1,
     "metaName" : "metaValue"]
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 133280317,
        "result": true
    }

DELTE: taskmetadata/taskmetadata
------------------

-  Purpose: **Remove task metadata by name**
-  Parameters:

   -  **task_id** (integer, required)
   -  **name** (string, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example to remove metada of a task by name:

.. code:: json

     [  1,
    "metaKey1"]
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 133280317,
        "result": true
    }
