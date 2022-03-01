Tags API Procedures
===================

GET: tags/alltags/:id
----------

-  Purpose: **Get all tags**
-  Parameters: none
-  Result on success: **List of tags**
-  Result on failure: **false|null**

Request example:

.. code:: json


Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "result": [
            {
                "id": "1",
                "name": "another tag",
                "project_id": "33"
            }
        ],
        "id": 45253426
    }

GET: tags/tagsbyproject
----------------

-  Purpose: **Get all tags for a given project**
-  Parameters:

   -  **project_id** (integer)

-  Result on success: **List of tags**
-  Result on failure: **false|null**

Request example:

.. code:: json

    [33]

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "result": [
            {
                "id": "1",
                "name": "some tag",
                "project_id": "33"
            }
        ],
        "id": 1217591720
    }

POST: tags/tag
---------

-  Purpose: **Create a new tag**
-  Parameters:

   -  **project_id** (integer)
   -  **tag** (string)

-  Result on success: **tag_id**
-  Result on failure: **false**

Request example:

.. code:: json

    [33,"some tag"]

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "result": 1,
        "id": 1775436017
    }

PUT: tags/Tag
---------

-  Purpose: **Rename a tag**
-  Parameters:

   -  **tag_id** (integer)
   -  **tag** (string)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

 ["1","another tag"]

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "result": true,
        "id": 2037516512
    }

DELTE: tags/Tag/:id
---------

-  Purpose: **removeTag**
-  Parameters:

   -  **tag_id** (integer)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json


Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "result": true,
        "id": 907581298
    }

POST: tags/tasktags
-----------

-  Purpose: **Assign/Create/Update tags for a task**
-  Parameters:

   -  **project_id** (integer)
   -  **task_id** (integer)
   -  **tags** List of tags ([]string)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

 [39,17,["tag1","tag2"]]

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "result": true,
        "id": 1524522873
    }

GET: tags/tasktags/:id
-----------

-  Purpose: **Get assigned tags to a task**
-  Parameters:

   -  **task_id** (integer)

-  Result on success: **Dictionary of tags**
-  Result on failure: **false|null**

Request example:

.. code:: json


Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "result": {
            "1": "tag1",
            "2": "tag2"
        },
        "id": 1667157705
    }
