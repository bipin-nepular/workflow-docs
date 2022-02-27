Project Permission API Procedures
=================================

Get: projectpermission/projectusers
---------------

-  Purpose: **Get all members of a project**
-  Parameters:

   -  **project_id** (integer, required)

-  Result on success: **Dictionary of user_id => user name**
-  Result on failure: **false**

Request example:

.. code:: json

     ["1"]

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1601016721,
        "result": {
            "1": "admin"
        }
    }

Get:  projectpermission/assignableusers
------------------

-  Purpose: **Get users that can be assigned to a task for a project**
   (all members except viewers)
-  Parameters:

   -  **project_id** (integer, required)
   -  **prepend_unassigned** (boolean, optional, default is false)

-  Result on success: **Dictionary of user_id => user name**
-  Result on failure: **false**

Request example:

.. code:: json

     ["1"]


Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 658294870,
        "result": {
            "1": "admin"
        }
    }

POST: projectpermission/projectuser/:project_id
--------------

-  Purpose: **Grant access to a project for a user**
-  Parameters:

   -  **project_id** (integer, required)
   -  **user_id** (integer, required)
   -  **role** (string, optional)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

   {
      "user_id" : 1,
      "role" : "project-manager"
   }

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1294688355,
        "result": true
    }

POST: projectpermission/projectgroup/:project_id
---------------

-  Purpose: **Grant access to a project for a group**
-  Parameters:

   -  **project_id** (integer, required)
   -  **group_id** (integer, required)
   -  **role** (string, optional)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

     {
     "group_id" : 1,
     "role" : "project-viewer"
     }
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1694959089,
        "result": true
    }

DELTE: projectpermission/projectuser/:project_id
-----------------

-  Purpose: **Revoke user access to a project**
-  Parameters:

   -  **project_id** (integer, required)
   -  **user_id** (integer, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

    {
    "user_id" : 1
    }
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 645233805,
        "result": true
    }

DELTE: projectpermission/projectgroup/:project_id
------------------

-  Purpose: **Revoke group access to a project**
-  Parameters:

   -  **project_id** (integer, required)
   -  **group_id** (integer, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

    {
    "group_id" : 1
    }
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 557146966,
        "result": true
    }

PUT: projectpermission/projectuserrole/:project_id
---------------------

-  Purpose: **Change role of a user for a project**
-  Parameters:

   -  **project_id** (integer, required)
   -  **user_id** (integer, required)
   -  **role** (string, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

    {
    "user_id" : 1,
    "user_role" : "project-viewer"
    }
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 193473170,
        "result": true
    }

PUT: projectpermission/projectgrouprole/:project_id
----------------------

-  Purpose: **Change role of a group for a project**
-  Parameters:

   -  **project_id** (integer, required)
   -  **group_id** (integer, required)
   -  **role** (string, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

    {
    "group_id" : 1,
    "group_role" : "project-viewer"
    }
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 2114673298,
        "result": true
    }

Get: projectpermission/projectuserrole/:project_id
------------------

-  Purpose: **Get the role of a user for a given project**
-  Parameters:

   -  **project_id** (integer, required)
   -  **user_id** (integer, required)

-  Result on success: **role name**
-  Result on failure: **false**

Request example:

.. code:: json
     
     {
     "user_id": 5
     }


Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 2114673298,
        "result": "project-viewer"
    }
