Column API Procedures
=====================

GET: column/columns
----------

-  Purpose: **Get all columns information for a given project**
-  Parameters:

   -  **project_id** (integer, required)

-  Result on success: **columns properties**
-  Result on failure: **empty list**

Request example:

.. code:: json

     {
         "project_id" : 1
     }
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 887036325,
        "result": [
            {
                "id": "1",
                "title": "Backlog",
                "position": "1",
                "project_id": "1",
                "task_limit": "0"
            },
            {
                "id": "2",
                "title": "Ready",
                "position": "2",
                "project_id": "1",
                "task_limit": "0"
            },
            {
                "id": "3",
                "title": "Work in progress",
                "position": "3",
                "project_id": "1",
                "task_limit": "0"
            }
        ]
    }

GET: column/column
---------

-  Purpose: **Get a single column**
-  Parameters:

   -  **column_id** (integer, required)

-  Result on success: **column properties**
-  Result on failure: **null**

Request example:

.. code:: json

  [ 2 ]  

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1242049935,
        "result": {
            "id": "2",
            "title": "Youpi",
            "position": "2",
            "project_id": "1",
            "task_limit": "5"
        }
    }

PUT: column/columnposition
--------------------

-  Purpose: **Change the column position**
-  Parameters:

   -  **project_id** (integer, required)
   -  **column_id** (integer, required)
   -  **position** (integer, required, must be >= 1)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json
    
     [ 1,
       2,
       3 ]
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 99275573,
        "result": true
    }

PUT: column/column
------------

-  Purpose: **Update column properties**
-  Parameters:

   -  **column_id** (integer, required)
   -  **title** (string, required)
   -  **task_limit** (integer, optional)
   -  **description** (string, optional)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json
        
         [ 2,
          "Boo",
           5 ]
          

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 480740641,
        "result": true
    }

POST: column/column
---------

-  Purpose: **Add a new column**
-  Parameters:

   -  **project_id** (integer, required)
   -  **title** (string, required)
   -  **task_limit** (integer, optional)
   -  **description** (string, optional)

-  Result on success: **column_id**
-  Result on failure: **false**

Request example:

.. code:: json
   
    [   1,
      "Boo" ]
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 638544704,
        "result": 5
    }

DELTE: column/column
------------

-  Purpose: **Remove a column**
-  Parameters:

   -  **column_id** (integer, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

   [ 1 ]

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1433237746,
        "result": true
    }
