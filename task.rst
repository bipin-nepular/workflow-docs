Task API Procedures
===================

POST: task/task
----------

-  Purpose: **Create a new task**
-  Parameters:

   -  **title** (string, required)
   -  **project_id** (integer, required)
   -  **color_id** (string, optional)
   -  **column_id** (integer, optional)
   -  **owner_id** (integer, optional)
   -  **creator_id** (integer, optional)
   -  **date_due**: ISO8601 format (string, optional)
   -  **description** Markdown content (string, optional)
   -  **category_id** (integer, optional)
   -  **score** (integer, optional)
   -  **swimlane_id** (integer, optional)
   -  **priority** (integer, optional)
   -  **recurrence_status** (integer, optional)
   -  **recurrence_trigger** (integer, optional)
   -  **recurrence_factor** (integer, optional)
   -  **recurrence_timeframe** (integer, optional)
   -  **recurrence_basedate** (integer, optional)
   -  **reference** (string, optional)
   -  **tags** ([]string, optional)
   -  **date_started**: ISO8601 format (string, optional)

-  Result on success: **task_id**
-  Result on failure: **false**

Request example:

.. code:: json

       {
            "owner_id": 1,
            "creator_id": 0,
            "date_due": "",
            "description": "",
            "category_id": 0,
            "score": 0,
            "title": "Test",
            "project_id": 1,
            "color_id": "green",
            "column_id": 2,
            "recurrence_status": 0,
            "recurrence_trigger": 0,
            "recurrence_factor": 0,
            "recurrence_timeframe": 0,
            "recurrence_basedate": 0 
            }
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1176509098,
        "result": 3
    }

GET: task/task/:task_id
-------

-  Purpose: **Get task by the unique id**
-  Parameters:

   -  **task_id** (integer, required)

-  Result on success: **task properties**
-  Result on failure: **null**

Request example:

.. code:: json


Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 700738119,
        "result": {
            "id": "1",
            "title": "Task #1",
            "description": "",
            "date_creation": "1409963206",
            "color_id": "blue",
            "project_id": "1",
            "column_id": "2",
            "owner_id": "1",
            "position": "1",
            "is_active": "1",
            "date_completed": null,
            "score": "0",
            "date_due": "0",
            "category_id": "0",
            "creator_id": "0",
            "date_modification": "1409963206",
            "reference": "",
            "date_started": null,
            "time_spent": "0",
            "time_estimated": "0",
            "swimlane_id": "0",
            "date_moved": "1430875287",
            "recurrence_status": "0",
            "recurrence_trigger": "0",
            "recurrence_factor": "0",
            "recurrence_timeframe": "0",
            "recurrence_basedate": "0",
            "recurrence_parent": null,
            "recurrence_child": null,
            "url": "http:\/\/127.0.0.1:8000\/?controller=task&action=show&task_id=1&project_id=1",
            "color": {
                "name": "Yellow",
                "background": "rgb(245, 247, 196)",
                "border": "rgb(223, 227, 45)"
            }
        }
    }

GET: task/taskbyreference
------------------

-  Purpose: **Get task by the external reference**
-  Parameters:

   -  **project_id** (integer, required)
   -  **reference** (string, required)

-  Result on success: **task properties**
-  Result on failure: **null**

Request example:

.. code:: json
           
           { 
           "project_id": 1,
            "reference": "TICKET-1234"
            }

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1992081213,
        "result": {
            "id": "5",
            "title": "Task with external ticket number",
            "description": "[Link to my ticket](http:\/\/my-ticketing-system\/1234)",
            "date_creation": "1434227446",
            "color_id": "yellow",
            "project_id": "1",
            "column_id": "1",
            "owner_id": "0",
            "position": "4",
            "is_active": "1",
            "date_completed": null,
            "score": "0",
            "date_due": "0",
            "category_id": "0",
            "creator_id": "0",
            "date_modification": "1434227446",
            "reference": "TICKET-1234",
            "date_started": null,
            "time_spent": "0",
            "time_estimated": "0",
            "swimlane_id": "0",
            "date_moved": "1434227446",
            "recurrence_status": "0",
            "recurrence_trigger": "0",
            "recurrence_factor": "0",
            "recurrence_timeframe": "0",
            "recurrence_basedate": "0",
            "recurrence_parent": null,
            "recurrence_child": null,
            "url": "http:\/\/127.0.0.1:8000\/?controller=task&action=show&task_id=5&project_id=1"
        }
    }

GET: task/alltasks
-----------

-  Purpose: **Get all available tasks**
-  Parameters:

   -  **project_id** (integer, required)
   -  **status_id**: The value 1 for active tasks and 0 for inactive
      (integer, required)

-  Result on success: **List of tasks**
-  Result on failure: **false**

Request example to fetch all tasks on the board:


 {"project_id": 1,
   "status_id": 1 }
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 133280317,
        "result": [
            {
                "id": "1",
                "title": "Task #1",
                "description": "",
                "date_creation": "1409961789",
                "color_id": "blue",
                "project_id": "1",
                "column_id": "2",
                "owner_id": "1",
                "position": "1",
                "is_active": "1",
                "date_completed": null,
                "score": "0",
                "date_due": "0",
                "category_id": "0",
                "creator_id": "0",
                "date_modification": "1409961789",
                "reference": "",
                "date_started": null,
                "time_spent": "0",
                "time_estimated": "0",
                "swimlane_id": "0",
                "date_moved": "1430783191",
                "recurrence_status": "0",
                "recurrence_trigger": "0",
                "recurrence_factor": "0",
                "recurrence_timeframe": "0",
                "recurrence_basedate": "0",
                "recurrence_parent": null,
                "recurrence_child": null,
                "priority": "0",
                "external_provider": null,
                "external_uri": null,
                "url": "http:\/\/127.0.0.1:8000\/?controller=task&action=show&task_id=1&project_id=1",
                "color": {
                    "name": "Blue",
                    "background": "rgb(219, 235, 255)",
                    "border": "rgb(168, 207, 255)"
                }
            },
            {
                "id": "2",
                "title": "Test",
                "description": "",
                "date_creation": "1409962115",
                "color_id": "green",
                "project_id": "1",
                "column_id": "2",
                "owner_id": "1",
                "position": "2",
                "is_active": "1",
                "date_completed": null,
                "score": "0",
                "date_due": "0",
                "category_id": "0",
                "creator_id": "0",
                "date_modification": "1409962115",
                "reference": "",
                "date_started": null,
                "time_spent": "0",
                "time_estimated": "0",
                "swimlane_id": "0",
                "date_moved": "1430783191",
                "recurrence_status": "0",
                "recurrence_trigger": "0",
                "recurrence_factor": "0",
                "recurrence_timeframe": "0",
                "recurrence_basedate": "0",
                "recurrence_parent": null,
                "recurrence_child": null,
                "priority": "0",
                "external_provider": null,
                "external_uri": null,
                "url": "http:\/\/127.0.0.1:8000\/?controller=task&action=show&task_id=2&project_id=1",
                "color": {
                    "name": "Green",
                    "background": "rgb(189, 244, 203)",
                    "border": "rgb(74, 227, 113)"
                }
            }
        ]
    }

GET: task/overduetasks
---------------

-  Purpose: **Get all overdue tasks**
-  Result on success: **List of tasks**
-  Result on failure: **false**

Request example to fetch all tasks on the board:

.. code:: json


Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 133280317,
        "result": [
            {
                "id": "1",
                "title": "Task #1",
                "date_due": "1409961789",
                "project_id": "1",
                "project_name": "Test",
                "assignee_username":"admin",
                "assignee_name": null
            },
            {
                "id": "2",
                "title": "Test",
                "date_due": "1409962115",
                "project_id": "1",
                "project_name": "Test",
                "assignee_username":"admin",
                "assignee_name": null
            }
        ]
    }

 GET: task/overduetasks
------------------------

-  Purpose: **Get all overdue tasks for a special project**
-  Result on success: **List of tasks**
-  Result on failure: **false**

Request example to fetch all tasks on the board:

.. code:: json
   
   {
   "project_id": 1
   }

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 133280317,
        "result": [
            {
                "id": "1",
                "title": "Task #1",
                "date_due": "1409961789",
                "project_id": "1",
                "project_name": "Test",
                "assignee_username":"admin",
                "assignee_name": null
            },
            {
                "id": "2",
                "title": "Test",
                "date_due": "1409962115",
                "project_id": "1",
                "project_name": "Test",
                "assignee_username":"admin",
                "assignee_name": null
            }
        ]
    }

PUT: task/task/:id
----------

-  Purpose: **Update a task**
-  Parameters:

   -  **id** (integer, required)
   -  **title** (string, optional)
   -  **color_id** (string, optional)
   -  **owner_id** (integer, optional)
   -  **date_due**: ISO8601 format (string, optional)
   -  **description** Markdown content (string, optional)
   -  **category_id** (integer, optional)
   -  **score** (integer, optional)
   -  **priority** (integer, optional)
   -  **recurrence_status** (integer, optional)
   -  **recurrence_trigger** (integer, optional)
   -  **recurrence_factor** (integer, optional)
   -  **recurrence_timeframe** (integer, optional)
   -  **recurrence_basedate** (integer, optional)
   -  **reference** (string, optional)
   -  **tags** ([]string, optional)
   -  **date_started**: ISO8601 format (string, optional)

-  Result on success: **true**
-  Result on failure: **false**

Request example to change the task color:

.. code:: json

     {"id": 1,
     "color_id": "blue"}
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1406803059,
        "result": true
    }

PUT: task/opentask/:task_id
--------

-  Purpose: **Set a task to the status open**
-  Parameters:

   -  **task_id** (integer, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json


Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1888531925,
        "result": true
    }

PUT: task/closetask/:id
---------

-  Purpose: **Set a task to the status close**
-  Parameters:

   -  **task_id** (integer, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1654396960,
        "result": true
    }

DELTE: task/task/:task_id
----------

-  Purpose: **Remove a task**
-  Parameters:

   -  **task_id** (integer, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json


Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1423501287,
        "result": true
    }

PUT: task/movetask/:task_id
----------------

-  Purpose: **Move a task to another column, position or swimlane inside
   the same board**
-  Parameters:

   -  **project_id** (integer, required)
   -  **task_id** (integer, required)
   -  **column_id** (integer, required)
   -  **position** (integer, required)
   -  **swimlane_id** (integer, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json
         
           { "project_id": 1,
            "column_id": 2,
            "position": 1,
            "swimlane_id": 1}

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 117211800,
        "result": true
    }

PUT: task/movetasktoproject/:task_id
-----------------

-  Purpose: **Move a task to another project**
-  Parameters:

   -  **task_id** (integer, required)
   -  **project_id** (integer, required)
   -  **swimlane_id** (integer, optional)
   -  **column_id** (integer, optional)
   -  **category_id** (integer, optional)
   -  **owner_id** (integer, optional)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

    {
    "project_id" :1 
    }
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 15775829,
        "result": true
    }


POST: task/duplicatetasktoproject/:task_id
----------------------

-  Purpose: **Duplicate Tasks to another column or project**
-  Parameters:

   -  **task_id** (integer, required)
   -  **project_id** (integer, required)
   -  **swimlane_id** (integer, optional)
   -  **column_id** (integer, optional)
   -  **category_id** (integer, optional)
   -  **owner_id** (integer, optional)

-  Result on success: **task_id**
-  Result on failure: **false**

Request example:

.. code:: json

    {
    "project_id" : 4
    }
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1662458687,
        "result": 6
    }

GET: task/tasks
-----------

-  Purpose: **Find tasks by using the search engine**
-  Parameters:

   -  **project_id** (integer, required)
   -  **query** (string, required)

-  Result on success: **list of tasks**
-  Result on failure: **false**

Request example:

.. code:: json

    {"project_id": 2,
     "query": "assignee:nobody"}
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1468511716,
        "result": [
            {
                "nb_comments": "0",
                "nb_files": "0",
                "nb_subtasks": "0",
                "nb_completed_subtasks": "0",
                "nb_links": "0",
                "nb_external_links": "0",
                "is_milestone": null,
                "id": "3",
                "reference": "",
                "title": "T3",
                "description": "",
                "date_creation": "1461365164",
                "date_modification": "1461365164",
                "date_completed": null,
                "date_started": null,
                "date_due": "0",
                "color_id": "yellow",
                "project_id": "2",
                "column_id": "5",
                "swimlane_id": "0",
                "owner_id": "0",
                "creator_id": "0"
             }
        ]
    }
