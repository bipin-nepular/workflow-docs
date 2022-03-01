Comment API Procedures
======================

POST: comment/comment/:task_id
-------------

-  Purpose: **Create a new comment**
-  Parameters:

   -  **task_id** (integer, required)
   -  **user_id** (integer, required)
   -  **content** Markdown content (string, required)

-  Result on success: **comment_id**
-  Result on failure: **false**

Request example:

.. code:: json

         {
            "user_id": 1,
            "content": "Comment #1"   }

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1580417921,
        "result": 11
    }

GET: comment/comment/:comment_id
----------

-  Purpose: **Get comment information**
-  Parameters:

   -  **comment_id** (integer, required)

-  Result on success: **comment properties**
-  Result on failure: **null**

Request example:

.. code:: json
          
  null
            

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 867839500,
        "result": {
            "id": "1",
            "task_id": "1",
            "user_id": "1",
            "date_creation": "1410881970",
            "comment": "Comment #1",
            "username": "admin",
            "name": null
        }
    }

GET: comment/allcomments
--------------

-  Purpose: **Get all available comments**
-  Parameters:

   -  **task_id** (integer, required)

-  Result on success: **List of comments**
-  Result on failure: **false**

Request example:

.. code:: json
           
 {"task_id": 1}
    
Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 148484683,
        "result": [
            {
                "id": "1",
                "date_creation": "1410882272",
                "task_id": "1",
                "user_id": "1",
                "comment": "Comment #1",
                "username": "admin",
                "name": null
            }
        ]
    }

PUT: comment/comment/:id
-------------

-  Purpose: **Update a comment**
-  Parameters:

   -  **id** (integer, required)
   -  **content** Markdown content (string, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

     { 
       "content": "Comment #1 updated"
        }

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1493368950,
        "result": true
    }

DELTE: comment/comment/:id
-------------

-  Purpose: **Remove a comment**
-  Parameters:

   -  **comment_id** (integer, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json
       
  null
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 328836871,
        "result": true
    }
