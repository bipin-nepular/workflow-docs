Introduction
============

User and application API
------------------------

There are two types of API access:

Application API
~~~~~~~~~~~~~~~

-  Access to the API with the user “jsonrpc” and the token available on
   the settings page
-  Access to all procedures
-  No permission checked
-  There is no user session on the server
-  No access to procedures that starts with “My…” (example: “getMe” or
   “getMyProjects”)
-  Example of possible clients: tools to migrate/import data, create
   tasks from another system, etc…

User API
~~~~~~~~

-  Access to the API with the user credentials (username and password)
-  You can also generate a personal access token instead of your
   password
-  Application role and project permissions are checked for each
   procedure
-  A user session is created on the server
-  Example of possible clients: native mobile/desktop application,
   command line utility, etc…

Security
--------

-  Always use HTTPS with a valid certificate (avoid clear text
   communication)
-  If you develop a mobile application, it's your responsability to store
   securely the user credentials on the device
-  After 3 authentication failures on the user API, the end-user have to
   unlock his account by using the login form



Protocol
--------

We uses the protocol Json-RPC to interact with external programs.

JSON-RPC is a remote procedure call protocol encoded in JSON. Almost the
same thing as XML-RPC but with the JSON format.

We use the `version 2 of the
protocol <http://www.jsonrpc.org/specification>`__. You must call the
API with a ``POST`` HTTP request.

Support batch requests, so you can make multiple API calls in a
single HTTP request. It’s particularly useful for mobile clients with
higher network latency.
