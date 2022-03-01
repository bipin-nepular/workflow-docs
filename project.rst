Project API Procedures
======================

POST: project/project
-------------

-  Purpose: **Create a new project**
-  Parameters:

   -  **name** (string, required)
   -  **description** (string, optional)
   -  **owner_id** (integer, optional)
   -  **identifier** (alphanumeric string, optional)
   -  **start_date** ISO8601 format (string, optional)
   -  **end_date** ISO8601 format (string, optional)

-  Result on success: **project_id**
-  Result on failure: **false**

Request example:

.. code:: json

     {"name": "PHP client"}
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1797076613,
        "result": 2
    }

GET: project/projectbyid/:id
--------------

-  Purpose: **Get project information**
-  Parameters:

   -  **project_id** (integer, required)

-  Result on success: **project properties**
-  Result on failure: **null**

Request example:

.. code:: json

     null
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 226760253,
        "result": {
            "id": "1",
            "name": "API test",
            "is_active": "1",
            "token": "",
            "last_modified": "1436119135",
            "is_public": "0",
            "is_private": "0",
            "default_swimlane": "Default swimlane",
            "show_default_swimlane": "1",
            "description": "test",
            "identifier": "",
            "url": {
                "board": "http:\/\/127.0.0.1:8000\/?controller=board&action=show&project_id=1",
                "calendar": "http:\/\/127.0.0.1:8000\/?controller=calendar&action=show&project_id=1",
                "list": "http:\/\/127.0.0.1:8000\/?controller=listing&action=show&project_id=1"
            }
        }
    }

GET: project/projectbyname
----------------

-  Purpose: **Get project information**
-  Parameters:

   -  **name** (string, required)

-  Result on success: **project properties**
-  Result on failure: **null**

Request example:

.. code:: json

     {"name": "Test"}


Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1620253806,
        "result": {
            "id": "1",
            "name": "Test",
            "is_active": "1",
            "token": "",
            "last_modified": "1436119135",
            "is_public": "0",
            "is_private": "0",
            "default_swimlane": "Default swimlane",
            "show_default_swimlane": "1",
            "description": "test",
            "identifier": "",
            "url": {
                "board": "http:\/\/127.0.0.1:8000\/?controller=board&action=show&project_id=1",
                "calendar": "http:\/\/127.0.0.1:8000\/?controller=calendar&action=show&project_id=1",
                "list": "http:\/\/127.0.0.1:8000\/?controller=listing&action=show&project_id=1"
            }
        }
    }

GET: project/projectbyidentifier
----------------------

-  Purpose: **Get project information**
-  Parameters:

   -  **identifier** (alphanumeric string, required)

-  Result on success: **project properties**
-  Result on failure: **null**

Request example:

.. code:: json

     {"identifier": "TEST"}


Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1620253806,
        "result": {
            "id": "1",
            "name": "Test",
            "is_active": "1",
            "token": "",
            "last_modified": "1436119135",
            "is_public": "0",
            "is_private": "0",
            "default_swimlane": "Default swimlane",
            "show_default_swimlane": "1",
            "description": "test",
            "identifier": "TEST",
            "url": {
                "board": "http:\/\/127.0.0.1:8000\/?controller=board&action=show&project_id=1",
                "calendar": "http:\/\/127.0.0.1:8000\/?controller=calendar&action=show&project_id=1",
                "list": "http:\/\/127.0.0.1:8000\/?controller=listing&action=show&project_id=1"
            }
        }
    }

GET: project/projectbyemail
-----------------

-  Purpose: **Get project information**
-  Parameters:

   -  **email** (string, required)

-  Result on success: **project properties**
-  Result on failure: **null**

Request example:

.. code:: json

     {"email": "my_project@my_domain.tld"}
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1620253806,
        "result": {
            "id": "1",
            "name": "Test",
            "is_active": "1",
            "token": "",
            "last_modified": "1436119135",
            "is_public": "0",
            "is_private": "0",
            "default_swimlane": "Default swimlane",
            "show_default_swimlane": "1",
            "description": "test",
            "identifier": "",
            "email": "my_project@my_domain.tld",
            "url": {
                "board": "http:\/\/127.0.0.1:8000\/?controller=board&action=show&project_id=1",
                "calendar": "http:\/\/127.0.0.1:8000\/?controller=calendar&action=show&project_id=1",
                "list": "http:\/\/127.0.0.1:8000\/?controller=listing&action=show&project_id=1"
            }
        }
    }

GET: project/allprojects
--------------

-  Purpose: **Get all available projects**
-  Parameters:

   -  **none**

-  Result on success: **List of projects**
-  Result on failure: **false**

Request example:

.. code:: json


Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 2134420212,
        "result": [
            {
                "id": "1",
                "name": "API test",
                "is_active": "1",
                "token": "",
                "last_modified": "1436119570",
                "is_public": "0",
                "is_private": "0",
                "default_swimlane": "Default swimlane",
                "show_default_swimlane": "1",
                "description": null,
                "identifier": "",
                "url": {
                    "board": "http:\/\/127.0.0.1:8000\/?controller=board&action=show&project_id=1",
                    "calendar": "http:\/\/127.0.0.1:8000\/?controller=calendar&action=show&project_id=1",
                    "list": "http:\/\/127.0.0.1:8000\/?controller=listing&action=show&project_id=1"
                }
            }
        ]
    }

PUT: project/project/:id
-------------

-  Purpose: **Update a project**
-  Parameters:

   -  **project_id** (integer, required)
   -  **name** (string, optional)
   -  **description** (string, optional)
   -  **owner_id** (integer, optional)
   -  **identifier** (string, optional)
   -  **start_date** ISO8601 format (string, optional)
   -  **end_date** ISO8601 format (string, optional)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

    {
      
     "name": "PHP client update"}
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1853996288,
        "result": true
    }

DELTE: project/project/:id
-------------

-  Purpose: **Remove a project**
-  Parameters: **project_id** (integer, required)
-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

     null
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 46285125,
        "result": true
    }

PUT: project/enable/:id
-------------

-  Purpose: **Enable a project**
-  Parameters:

   -  **project_id** (integer, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

    


Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1775494839,
        "result": true
    }


PUT: project/disable/:id
--------------

-  Purpose: **Disable a project**
-  Parameters:

   -  **project_id** (integer, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

     

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1734202312,
        "result": true
    }



PUT: project/enablepublicaccess/:id
-------------------------

-  Purpose: **Enable public access for a given project**
-  Parameters:

   -  **project_id** (integer, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

 
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 103792571,
        "result": true
    }

PUT: project/disablepublicaccess/:id
--------------------------

-  Purpose: **Disable public access for a given project**
-  Parameters:

   -  **project_id** (integer, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

    


Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 942472945,
        "result": true
    }

GET: project/projectactivity/:id
------------------

-  Purpose: **Get activity stream for a project**
-  Parameters:

   -  **project_id** (integer, required)

-  Result on success: **List of events**
-  Result on failure: **false**

Request example:


    

GET: project/projectactivities
--------------------

-  Purpose: **Get Activityfeed for Project(s)**
-  Parameters:

   -  **project_ids** (integer array, required)

-  Result on success: **List of events**
-  Result on failure: **false**

Request example:

.. code:: json

     { "project_ids": [1,2]  }
    
