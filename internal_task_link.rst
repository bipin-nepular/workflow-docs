Internal Task Link API Procedures
=================================

POST: Internal/tasklink
--------------

-  Purpose: **Create a link between two tasks**
-  Parameters:

   -  **task_id** (integer, required)
   -  **opposite_task_id** (integer, required)
   -  **link_id** (integer, required)

-  Result on success: **task_link_id**
-  Result on failure: **false**

Request example:

.. code:: json

        [ 2,
          3,
          1 ]
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 509742912,
        "result": 1
    }

PUT: Internal/tasklink
--------------

-  Purpose: **Update task link**
-  Parameters:

   -  **task_link_id** (integer, required)
   -  **task_id** (integer, required)
   -  **opposite_task_id** (integer, required)
   -  **link_id** (integer, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json
         
         [  1,
            2,
            4,
            2 ] 

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 669037109,
        "result": true
    }

GET: Internal/tasklinkbyid
---------------

-  Purpose: **Get a task link**
-  Parameters:

   -  **task_link_id** (integer, required)

-  Result on success: **task link properties**
-  Result on failure: **false**

Request example:

.. code:: json

     [ 1 ]

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 809885202,
        "result": {
            "id": "1",
            "link_id": "1",
            "task_id": "2",
            "opposite_task_id": "3"
        }
    }

GET: Internal/alltasklinks
---------------

-  Purpose: **Get all links related to a task**
-  Parameters:

   -  **task_id** (integer, required)

-  Result on success: **list of task link**
-  Result on failure: **false**

Request example:

.. code:: json

   [ 2 ]
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 810848359,
        "result": [
            {
                "id": "1",
                "task_id": "3",
                "label": "relates to",
                "title": "B",
                "is_active": "1",
                "project_id": "1",
                "task_time_spent": "0",
                "task_time_estimated": "0",
                "task_assignee_id": "0",
                "task_assignee_username": null,
                "task_assignee_name": null,
                "column_title": "Backlog"
            }
        ]
    }

DELTE: Internal/tasklink
--------------

-  Purpose: **Remove a link between two tasks**
-  Parameters:

   -  **task_link_id** (integer, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

    [ 1 ]

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 473028226,
        "result": true
    }
