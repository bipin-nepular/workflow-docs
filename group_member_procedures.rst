Group Member API Procedures
===========================

GET: groupmember/membergroups/:user_id
---------------

-  Purpose: **Get all groups for a given user**
-  Parameters:

   -  **user_id** (integer, required)

-  Result on success: **List of groups**
-  Result on failure: **false**

Request example:

.. code:: json
         
 

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1987176726,
        "result": [
            {
                "id": "1",
                "name": "My Group A"
            }
        ]
    }

GET: Groupmember/groupmembers/:group_id
---------------

-  Purpose: **Get all members of a group**
-  Parameters:

   -  **group_id** (integer, required)

-  Result on success: **List of users**
-  Result on failure: **false**

Request example:

.. code:: json

      

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1987176726,
        "result": [
            {
                "group_id": "1",
                "user_id": "1",
                "id": "1",
                "username": "admin",
                "is_ldap_user": "0",
                "name": null,
                "email": null,
                "notifications_enabled": "0",
                "timezone": null,
                "language": null,
                "disable_login_form": "0",
                "notifications_filter": "4",
                "nb_failed_login": "0",
                "lock_expiration_date": "0",
                "is_project_admin": "0",
                "gitlab_id": null,
                "role": "app-admin"
            }
        ]
    }

POST: groupmember/groupmember/:group_id
--------------

-  Purpose: **Add a user to a group**
-  Parameters:

   -  **group_id** (integer, required)
   -  **user_id** (integer, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

     {
     "user_id" :  1
     }
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1589058273,
        "result": true
    }

DELTE: groupmember/groupmember/:group_id
-----------------

-  Purpose: **Remove a user from a group**
-  Parameters:

   -  **group_id** (integer, required)
   -  **user_id** (integer, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

     {
     "user_id" :1
     }

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1730416406,
        "result": true
    }

GET: groupmember/isgroupmember/:group_id
-------------

-  Purpose: **Check if a user is member of a group**
-  Parameters:

   -  **group_id** (integer, required)
   -  **user_id** (integer, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

         {
           "user_id": 1
         }

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1052800865,
        "result": false
    }
