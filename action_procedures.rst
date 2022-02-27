Automatic Actions API Procedures
================================

GET: /automatic/availableactions
-------------------

-  Purpose: **Get list of available automatic actions**
-  Parameters: none
-  Result on success: **list of actions**
-  Result on failure: **false**

Request example:

.. code:: json

    null

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1217735483,
        "result": {
            "\Workflow\Action\TaskLogMoveAnotherColumn": "Add a comment logging moving the task between columns",
            "\Workflow\Action\TaskAssignColorUser": "Assign a color to a specific user",
            "\Workflow\Action\TaskAssignColorColumn": "Assign a color when the task is moved to a specific column",
            "\Workflow\Action\TaskAssignCategoryColor": "Assign automatically a category based on a color",
            "\Workflow\Action\TaskAssignColorCategory": "Assign automatically a color based on a category",
            "\Workflow\Action\TaskAssignSpecificUser": "Assign the task to a specific user",
            "\Workflow\Action\TaskAssignCurrentUser": "Assign the task to the person who does the action",
            "\Workflow\Action\TaskUpdateStartDate": "Automatically update the start date",
            "\Workflow\Action\TaskAssignUser": "Change the assignee based on an external username",
            "\Workflow\Action\TaskAssignCategoryLabel": "Change the category based on an external label",
            "\Workflow\Action\TaskClose": "Close a task",
            "\Workflow\Action\CommentCreation": "Create a comment from an external provider",
            "\Workflow\Action\TaskCreation": "Create a task from an external provider",
            "\Workflow\Action\TaskDuplicateAnotherProject": "Duplicate the task to another project",
            "\Workflow\Action\TaskMoveColumnAssigned": "Move the task to another column when assigned to a user",
            "\Workflow\Action\TaskMoveColumnUnAssigned": "Move the task to another column when assignee is cleared",
            "\Workflow\Action\TaskMoveAnotherProject": "Move the task to another project",
            "\Workflow\Action\TaskOpen": "Open a task"
        }
    }

GET: /automatic/availableactionevents
------------------------

-  Purpose: **Get list of available events for actions**
-  Parameters: none
-  Result on success: **list of events**
-  Result on failure: **false**

Request example:

.. code:: json

    null

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 2116665643,
        "result": {
            "bitbucket.webhook.commit": "Bitbucket commit received",
            "task.close": "Closing a task",
            "github.webhook.commit": "Github commit received",
            "github.webhook.issue.assignee": "Github issue assignee change",
            "github.webhook.issue.closed": "Github issue closed",
            "github.webhook.issue.commented": "Github issue comment created",
            "github.webhook.issue.label": "Github issue label change",
            "github.webhook.issue.opened": "Github issue opened",
            "github.webhook.issue.reopened": "Github issue reopened",
            "gitlab.webhook.commit": "Gitlab commit received",
            "gitlab.webhook.issue.closed": "Gitlab issue closed",
            "gitlab.webhook.issue.opened": "Gitlab issue opened",
            "task.move.column": "Move a task to another column",
            "task.open": "Open a closed task",
            "task.assignee_change": "Task assignee change",
            "task.create": "Task creation",
            "task.create_update": "Task creation or modification",
            "task.update": "Task modification"
        }
    }

GET: automatic/compatibleactionevents
-------------------------

-  Purpose: **Get list of events compatible with an action**
-  Parameters:

   -  **action_name** (string, required)

-  Result on success: **list of events**
-  Result on failure: **false**

Request example:

.. code:: json

     
     ["\\Kanboard\\Action\\TaskClose"]
   

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 899370297,
        "result": {
            "bitbucket.webhook.commit": "Bitbucket commit received",
            "github.webhook.commit": "Github commit received",
            "github.webhook.issue.closed": "Github issue closed",
            "gitlab.webhook.commit": "Gitlab commit received",
            "gitlab.webhook.issue.closed": "Gitlab issue closed",
            "task.move.column": "Move a task to another column"
        }
    }

GET: automatic/actions/:project_id
----------

-  Purpose: **Get list of actions for a project**
-  Parameters:

   -  **project_id** (integer, required)

-  Result on success: **list of actions properties**
-  Result on failure: **false**

Request example:

.. code:: json

    
    null
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1433237746,
        "result": [
            {
                "id" : "13",
                "project_id" : "2",
                "event_name" : "task.move.column",
                "action_name" : "\Workflow\Action\TaskAssignSpecificUser",
                "params" : {
                    "column_id" : "5",
                    "user_id" : "1"
                }
            }
        ]
    }

POST: automatic/action/:project_id
------------

-  Purpose: **Create an action**
-  Parameters:

   -  **project_id** (integer, required)
   -  **event_name** (string, required)
   -  **action_name** (string, required)
   -  **params** (key/value parameters, required)

-  Result on success: **action_id**
-  Result on failure: **false**

Request example:

.. code:: json

    {
        "event_name" : "task.move.column",
        "action_name" : "\\Kanboard\\Action\\TaskAssignSpecificUser",
        "params" : {
            "column_id" : "3",
            "user_id" : "2"
            }
     }
        
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1433237746,
        "result": 14
    }

DELTE: automatic/action/:id
------------

-  Purpose: **Remove an action**
-  Parameters:

   -  **action_id** (integer, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json
     null
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1510741671,
        "result": true
    }
