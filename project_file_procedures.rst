Project File API Procedures
===========================

POST: projectfile/projectfile
-----------------

-  Purpose: **Create and upload a new project attachment**
-  Parameters:

   -  **project_id** (integer, required)
   -  **filename** (integer, required)
   -  **blob** File content encoded in base64 (string, required)

-  Result on success: **file_id**
-  Result on failure: **false**
-  Note: **The maximum file size depends of your PHP configuration, this
   method should not be used to upload large files**

Request example:

.. code:: json

     [     1,
          "My file",
          "cGxhaW4gdGV4dCBmaWxl"
        ]  

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 94500810,
        "result": 1
    }

GET: projectfile/allprojectfiles
------------------

-  Purpose: **Get all files attached to a project**
-  Parameters:

   -  **project_id** (integer, required)

-  Result on success: **list of files**
-  Result on failure: **false**

Request example:

.. code:: json
    
     {"project_id": 1 }
    }

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
                "project_id": "1",
                "date": "1432509941",
                "user_id": "0",
                "size": "15",
                "username": null,
                "user_name": null
            }
        ]
    }

GET: projectfile/projectfile
--------------

-  Purpose: **Get file information**
-  Parameters:

   -  **project_id** (integer, required)
   -  **file_id** (integer, required)

-  Result on success: **file properties**
-  Result on failure: **false**

Request example:

.. code:: json
        [    
        "42",
        "1"
        ]

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
            "project_id": "1",
            "date": "1432509941",
            "user_id": "0",
            "size": "15"
        }
    }

GET: projectfile/projectfile
-------------------

-  Purpose: **Download project file contents (encoded in base64)**
-  Parameters:

   -  **project_id** (integer, required)
   -  **file_id** (integer, required)

-  Result on success: **base64 encoded string**
-  Result on failure: **empty string**

Request example:

.. code:: json

       [    "1",
            "1"   ]

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 235943344,
        "result": "cGxhaW4gdGV4dCBmaWxl"
    }

DELTE: projectfile/projectfile
-----------------

-  Purpose: **Remove a file associated to a project**
-  Parameters:

   -  **project_id** (integer, required)
   -  **file_id** (integer, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json
        [
            "1",
            "1"
                 ]

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 447036524,
        "result": true
    }

DELTE: projectfile/allprojectfiles
---------------------

-  Purpose: **Remove all files associated to a project**
-  Parameters:

   -  **project_id** (integer, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

     { "project_id": 1 }

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 593312993,
        "result": true
    }
