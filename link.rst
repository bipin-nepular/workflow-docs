Link API Procedures
===================


GET: link/alllinks
-----------

-  Purpose: **Get the list of possible relations between tasks**
-  Parameters: none
-  Result on success: **List of links**
-  Result on failure: **false**

Request example:

.. code:: json


Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 113057196,
        "result": [
            {
                "id": "1",
                "label": "relates to",
                "opposite_id": "0"
            },
            {
                "id": "2",
                "label": "blocks",
                "opposite_id": "3"
            },
            {
                "id": "3",
                "label": "is blocked by",
                "opposite_id": "2"
            },
            {
                "id": "4",
                "label": "duplicates",
                "opposite_id": "5"
            },
            {
                "id": "5",
                "label": "is duplicated by",
                "opposite_id": "4"
            },
            {
                "id": "6",
                "label": "is a child of",
                "opposite_id": "7"
            },
            {
                "id": "7",
                "label": "is a parent of",
                "opposite_id": "6"
            },
            {
                "id": "8",
                "label": "targets milestone",
                "opposite_id": "9"
            },
            {
                "id": "9",
                "label": "is a milestone of",
                "opposite_id": "8"
            },
            {
                "id": "10",
                "label": "fixes",
                "opposite_id": "11"
            },
            {
                "id": "11",
                "label": "is fixed by",
                "opposite_id": "10"
            }
        ]
    }

GET: link/oppositelinkid
-----------------

-  Purpose: **Get the opposite link id of a task link**
-  Parameters:

   -  **link_id** (integer, required)

-  Result on success: **link_id**
-  Result on failure: **false**

Request example:

.. code:: json

     [ 2 ]

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 407062448,
        "result": "3"
    }

GET: link/linkbylabel
--------------

-  Purpose: **Get a link by label**
-  Parameters:

   -  **label** (integer, required)

-  Result on success: **link properties**
-  Result on failure: **false**

Request example:

.. code:: json
    
  ["blocks"]

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1796123316,
        "result": {
            "id": "2",
            "label": "blocks",
            "opposite_id": "3"
        }
    }

GET: link/linkbyid
-----------

-  Purpose: **Get a link by id**
-  Parameters:

   -  **link_id** (integer, required)

-  Result on success: **link properties**
-  Result on failure: **false**

Request example:

.. code:: json
   
  [ 4 ]

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1190238402,
        "result": {
            "id": "4",
            "label": "duplicates",
            "opposite_id": "5"
        }
    }

POST: link/task
----------

-  Purpose: **Create a new task relation**
-  Parameters:

   -  **label** (integer, required)
   -  **opposite_label** (integer, optional)

-  Result on success: **link_id**
-  Result on failure: **false**

Request example:

.. code:: json

     [ "foo",
       "bar" ]

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 1040237496,
        "result": 13
    }

PUT: link/link
----------

-  Purpose: **Update a link**
-  Parameters:

   -  **link_id** (integer, required)
   -  **opposite_link_id** (integer, required)
   -  **label** (string, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json
          [
            "14",
            "12",
            "boo"
                 ]

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 2110446926,
        "result": true
    }

DELTE: link/link
----------

-  Purpose: **Remove a link**
-  Parameters:

   -  **link_id** (integer, required)

-  Result on success: **true**
-  Result on failure: **false**

Request example:

.. code:: json

     ["14"]

Response example:

.. code:: json

    {
        "jsonrpc": "2.0",
        "id": 2136522739,
        "result": true
    }
