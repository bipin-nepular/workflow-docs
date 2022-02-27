User API Procedures
===================

POST: user/user
----------

-  Purpose: **Create a new user**
-  Parameters:

   -  **username** Must be unique (string, required)
   -  **password** Must have at least 6 characters (string, required)
   -  **name** (string, optional)
   -  **email** (string, optional)
   -  **role** (string, optional, example: app-admin, app-manager,
      app-user)

-  Result on success: **user_id**
-  Result on failure: **false**

Request example:

.. code:: json
       
        {"username": "biloute",
        "password": "123456"}


Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1518863034,
        "result": 22
    }

POST: user/ldapuser
--------------

-  Purpose: **Create a new user authentified by LDAP**
-  Parameters:

   -  **username** (string, required)

-  Result on success: **user_id**
-  Result on failure: **false**

The user will only be created if he is found on the LDAP server. This
method works only with LDAP authentication configured in proxy or
anonymous mode.

Request example:

.. code:: json
      {
         "username":"nepular"
      }
      

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1518863034,
        "result": 22
    }

GET: user/user/:user_id
-------

-  Purpose: **Get user information**
-  Parameters:

   -  **user_id** (integer, required)

-  Result on success: **user properties**
-  Result on failure: **null**

Request example:

.. code:: json

    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1769674781,
        "result": {
            "id": "1",
            "username": "biloute",
            "password": "$2y$10$dRs6pPoBu935RpmsrhmbjevJH5MgZ7Kr9QrnVINwwyZ3.MOwqg.0m",
            "role": "app-user",
            "is_ldap_user": "0",
            "name": "",
            "email": "",
            "google_id": null,
            "github_id": null,
            "notifications_enabled": "0"
        }
    }

GET: user/userbyname
-------------

-  Purpose: **Get user information**
-  Parameters:

   -  **username** (string, required)

-  Result on success: **user properties**
-  Result on failure: **null**

Request example:

.. code:: json
      {
         "username" : "nepular"
      }


Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1769674782,
        "result": {
            "id": "1",
            "username": "biloute",
            "password": "$2y$10$dRs6pPoBu935RpmsrhmbjevJH5MgZ7Kr9QrnVINwwyZ3.MOwqg.0m",
            "role": "app-user",
            "is_ldap_user": "0",
            "name": "",
            "email": "",
            "google_id": null,
            "github_id": null,
            "notifications_enabled": "0"
        }
    }

GET: user/allusers
-----------

-  Purpose: **Get all available users**
-  Parameters:

   -  **none**

-  Result on success: **List of users**
-  Result on failure: **false**

Request example:

.. code:: json


Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1438712131,
        "result": [
            {
                "id": "1",
                "username": "biloute",
                "name": "",
                "email": "",
                "role": "app-user",
                "is_ldap_user": "0",
                "notifications_enabled": "0",
                "google_id": null,
                "github_id": null
            }
        ]
    }


PUT: user/user/:id
----------

-  Purpose: **Update a user**
-  Parameters:

   -  **id** (integer)
   -  **username** (string, optional)
   -  **name** (string, optional)
   -  **email** (string, optional)
   -  **role** (string, optional, example: app-admin, app-manager,
      app-user)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

     {
      "username" : "nepular",
      "name" : "updated name",
      "email": "updated@email.com",
      "role": "app-manager",
      }
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 322123657,
        "result": true
    }

DELTE: user/user/:user_id
----------

-  Purpose: **Remove a user**
-  Parameters:

   -  **user_id** (integer, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json


Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 2094191872,
        "result": true
    }

PUT: user/disableuser/:id
-----------

-  Purpose: **Disable a user**
-  Parameters:

   -  **user_id** (integer, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json
     

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 2094191872,
        "result": true
    }

PUT: user/enableuser/:user_id
----------

-  Purpose: **Enable a user**
-  Parameters:

   -  **user_id** (integer, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

   
Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 2094191872,
        "result": true
    }

GET: user/isactiveuser/:user_id
------------

-  Purpose: **Check if a user is active**
-  Parameters:

   -  **user_id** (integer, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json


Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 2094191872,
        "result": true
    }
