.. .. include:: /includes/unicode-checkmark.rst

.. _crafter-studio-api-group-get-all:

==========
Get Groups
==========

Get all Crafter Studio groups with an optional range for pagination.

--------------------
Resource Information
--------------------

+----------------------------+-------------------------------------------------------------------+
|| HTTP Verb                 || GET                                                              |
+----------------------------+-------------------------------------------------------------------+
|| URL                       || ``/api/1/services/api/1/group/get-all.json``                     |
+----------------------------+-------------------------------------------------------------------+
|| Response Formats          || ``JSON``                                                         |
+----------------------------+-------------------------------------------------------------------+
|| Required Role             || Admin                                                            |
+----------------------------+-------------------------------------------------------------------+

----------
Parameters
----------

+---------------+-------------+---------------+--------------------------------------------------+
|| Name         || Type       || Required     || Description                                     |
+===============+=============+===============+==================================================+
|| start        || Integer    ||              || Start offset                                    |
+---------------+-------------+---------------+--------------------------------------------------+
|| number       || Integer    ||              || Number of records to retrieve                   |
+---------------+-------------+---------------+--------------------------------------------------+

-------
Example
-------

.. code-block:: guess

	GET .../api/1/services/api/1/group/get-all.json?start=0&number=25

.. code-block:: json

  {
    "sites" :
      [
        {
          "site_id" : "site 1",
          "groups" :
            [
              {
                "group_name" : "group1",
                "description" : "desc1"
              },
              {
                "group_name" : "group2",
                "description" : "desc2"
              }
            ]
        },
        {
           "site_id" : "site 2",
          "groups" :
            [
              {
                "group_name" : "group1",
                "description" : "desc1"
              },
              {
                "group_name" : "group2",
                "description" : "desc2"
              }
            ]
       }
    ]
  }

--------
Response
--------

+---------+-----------------------------------------------+---------------------------------------------------+
|| Status || Location                                     || Response Body                                    |
+=========+===============================================+===================================================+
|| 200    || ``.../group/get-all.json?start=0&number=25`` || See example above.                               |
+---------+-----------------------------------------------+---------------------------------------------------+
|| 400    ||                                              || ``{ "message" : "Invalid parameter(s)" }``       |
+---------+-----------------------------------------------+---------------------------------------------------+
|| 401    ||                                              || ``{ "message" : "Unauthorized" }``               |
+---------+-----------------------------------------------+---------------------------------------------------+
|| 500    ||                                              || ``{ "message" : "Internal server error" }``      |
+---------+-----------------------------------------------+---------------------------------------------------+
