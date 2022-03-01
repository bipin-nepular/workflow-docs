Subtask API Procedures
======================


POST: subtask/subtask
-------------

-  Purpose: **Create a new subtask**
-  Parameters:

   -  **task_id** (integer, required)
   -  **title** (integer, required)
   -  **user_id** (int, optional)
   -  **time_estimated** (int, optional)
   -  **time_spent** (int, optional)
   -  **status** (int, optional)

-  Result on success: **subtask_id**
-  Result on failure: **false**

Request example:

.. code:: json
       
        {"task_id": 1,
          "title": "Subtask #1"}
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 2041554661,
        "result": 45
    }

GET: subtask/subtask
----------

-  Purpose: **Get subtask information**
-  Parameters:

   -  **subtask_id** (integer)

-  Result on success: **subtask properties**
-  Result on failure: **null**

Request example:

.. code:: json

     {"subtask_id": 1 }
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 133184525,
        "result": {
            "id": "1",
            "title": "Subtask #1",
            "status": "0",
            "time_estimated": "0",
            "time_spent": "0",
            "task_id": "1",
            "user_id": "0"
        }
    }

GET: subtask/allsubtasks
--------------

-  Purpose: **Get all available subtasks**
-  Parameters:

   -  **task_id** (integer, required)

-  Result on success: **List of subtasks**
-  Result on failure: **false**

Request example:

.. code:: json

     {"task_id": 1}
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 2087700490,
        "result": [
            {
                "id": "1",
                "title": "Subtask #1",
                "status": "0",
                "time_estimated": "0",
                "time_spent": "0",
                "task_id": "1",
                "user_id": "0",
                "username": null,
                "name": null,
                "status_name": "Todo"
            }
        ]
    }

PUT: subtask/subtask
-------------

-  Purpose: **Update a subtask**
-  Parameters:

   -  **id** (integer, required)
   -  **task_id** (integer, required)
   -  **title** (integer, optional)
   -  **user_id** (integer, optional)
   -  **time_estimated** (integer, optional)
   -  **time_spent** (integer, optional)
   -  **status** (integer, optional)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

     {"id": 1,
      "task_id": 1,
      "status": 1,
      "time_spent": 5,
        "user_id": 1}
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 191749979,
        "result": true
    }

DELTE: subtask/subtask
-------------

-  Purpose: **Remove a subtask**
-  Parameters:

   -  **subtask_id** (integer, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

     {"subtask_id": 1}
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1382487306,
        "result": true
    }
