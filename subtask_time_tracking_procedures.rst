Subtask Time Tracking API procedures
====================================

GET: subtaskttime/subtasktimer
---------------

-  Purpose: **Check if a timer is started for the given subtask and
   user**
-  Parameters:

   -  **subtask_id** (integer, required)
   -  **user_id** (integer, optional)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

    [2,4]

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "result": true,
        "id": 1786995697
    }

PUT: subtaskttime/subtaskstarttime
-------------------

-  Purpose: **Start subtask timer for a user**
-  Parameters:

   -  **subtask_id** (integer, required)
   -  **user_id** (integer, optional)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

    [2,4]

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "result": true,
        "id": 1168991769
    }

PUT: subtaskttime/subtaskendtime
-----------------

-  Purpose: **Stop subtask timer for a user**
-  Parameters:

   -  **subtask_id** (integer, required)
   -  **user_id** (integer, optional)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

  [2,4]

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "result": true,
        "id": 1026607603
    }

GET: subtaskttime/subtasktimespent
-------------------

-  Purpose: **Get time spent on a subtask for a user**
-  Parameters:

   -  **subtask_id** (integer, required)
   -  **user_id** (integer, optional)

-  Result on success: **number of hours**
-  Result on failure: **false**

Request example:

.. code:: json

    [2,4]

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "result": 1.5,
        "id": 738527378
    }
