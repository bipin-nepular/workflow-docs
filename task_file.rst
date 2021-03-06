Task File API Procedures
========================

POST: taskfile/taskfile
--------------

-  Purpose: **Create and upload a new task attachment**
-  Parameters:

   -  **project_id** (integer, required)
   -  **task_id** (integer, required)
   -  **filename** (integer, required)
   -  **blob** File content encoded in base64 (string, required)

-  Result on success: **file_id**
-  Result on failure: **false**
-  Note: **The maximum file size depends of your PHP configuration, this
   method should not be used to upload large files**

Request example:

.. code:: json

     [ 1,
       1,
      "My file",
      "cGxhaW4gdGV4dCBmaWxl"]
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 94500810,
        "result": 1
    }

GET: taskfile/alltaskfiles/:id
---------------

-  Purpose: **Get all files attached to task**
-  Parameters:

   -  **task_id** (integer, required)

-  Result on success: **list of files**
-  Result on failure: **false**

Request example:

.. code:: json


Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1880662820,
        "result": [
            {
                "id": "1",
                "name": "My file",
                "path": "1\/1\/0db4d0a897a4c852f6e12f0239d4805f7b4ab596",
                "is_image": "0",
                "task_id": "1",
                "date": "1432509941",
                "user_id": "0",
                "size": "15",
                "username": null,
                "user_name": null
            }
        ]
    }

GET: taskfile/taskFile/:id
-----------

-  Purpose: **Get file information**
-  Parameters:

   -  **file_id** (integer, required)

-  Result on success: **file properties**
-  Result on failure: **false**

Request example:

.. code:: json


Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 318676852,
        "result": {
            "id": "1",
            "name": "My file",
            "path": "1\/1\/0db4d0a897a4c852f6e12f0239d4805f7b4ab596",
            "is_image": "0",
            "task_id": "1",
            "date": "1432509941",
            "user_id": "0",
            "size": "15"
        }
    }

POST: taskfile/taskfile/:id
----------------

-  Purpose: **Download file contents (encoded in base64)**
-  Parameters:

   -  **file_id** (integer, required)

-  Result on success: **base64 encoded string**
-  Result on failure: **empty string**

Request example:

.. code:: json


Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 235943344,
        "result": "cGxhaW4gdGV4dCBmaWxl"
    }

DELTE: taskfile/taskfile/:id
--------------

-  Purpose: **Remove file**
-  Parameters:

   -  **file_id** (integer, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json


Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 447036524,
        "result": true
    }

DELTE: taskfile/alltaskfiles
------------------

-  Purpose: **Remove all files associated to a task**
-  Parameters:

   -  **task_id** (integer, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "method": "removeAllTaskFiles",
        "id": 593312993,
        "params": {
            "task_id": 1
        }
    }

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 593312993,
        "result": true
    }
