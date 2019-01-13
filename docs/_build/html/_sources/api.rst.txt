API Refrence
============

The following documentation defines all of the usable routes in the Zane API.

.. warning::

  All routes use the base url of /api/v0/

Information Routes
------------------

.. http:get:: /status

  This returns the API's current status.

  **Example Request**:

  .. sourcecode:: http

    GET /status HTTP

  **Example response**:

  .. sourcecode:: http

    HTTP 200 OK
    Content-Type: application/json

    {
      'code': 200
      'message': 'The API is functioning okay.'
    }

  :statuscode 200: The api is functioning correctly
  :statuscode 404: The API functionality is currently disabled.
