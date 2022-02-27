Category API Procedures
=======================

POST: category/category
--------------

-  Purpose: **Create a new category**
-  Parameters:
-  **project_id** (integer, required)

-  **name** (string, required, must be unique for the given project)

-  Result on success: **category_id**
-  Result on failure: **false**

Request example:

.. code:: json
   
   {
     "name": "Super category",
   }

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 541909890,
        "result": 4
    }

GET: category/category/:id
-----------

-  Purpose: **Get category information**
-  Parameters:

   -  **category_id** (integer, required)

-  Result on success: **category properties**
-  Result on failure: **null**

Request example:

.. code:: json
           
   

Response example:

.. code:: json

    {

        "jsonrpc": "2.0",
        "id": 203539163,
        "result": {
            "id": "1",
            "name": "Super category",
            "project_id": "1"
        }
    }

GET: category/allcategories
----------------

-  Purpose: **Get all available categories**
-  Parameters:

   -  **project_id** (integer, required)

-  Result on success: **List of categories**
-  Result on failure: **false**

Request example:

.. code:: json
 
      {"project_id": 1}
        
   

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1261777968,
        "result": [
            {
                "id": "1",
                "name": "Super category",
                "project_id": "1"
            }
        ]
    }

PUT: category/category
--------------

-  Purpose: **Update a category**
-  Parameters:

   -  **id** (integer, required)
   -  **name** (string, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

            {"id": 1,
            "name": "Renamed category"}

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 570195391,
        "result": true
    }

DELTE: category/category
--------------

-  Purpose: **Remove a category**
-  Parameters:

   -  **category_id** (integer)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

  {"category_id": 1}
    

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 88225706,
        "result": true
    }
