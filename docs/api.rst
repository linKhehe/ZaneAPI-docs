API Refrence
============

The following documentation defines all of the usable routes in the Zane API.

.. warning::

  All routes use the base url of /api/v0/

Information Routes
------------------

This section outlines all of the routes used as information for the API.

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

Image Manipulation
------------------

This section outlines all of the routs used for image manipulation.

.. http:post:: /invert

  This returns an inverted version if the input image.
  If the image is larger than 512px in width or height,
  the image will be sampled down to that size while
  preserving aspect ratio.

  **Example Request**:

  .. sourcecode:: http

    POST /invert HTTP
    Accept: image/jpeg, image/png

  **Example response**:

  .. sourcecode:: http

    HTTP 200 OK
    Content-Type: image/png
    
    (image as bytes)

 :statuscode 200: Image manipulation is functioning correctly and has completed.
 :statuscode 404: The API functionality is currently disabled.
 :statuscode 500: The current endpoint is currently broken due to internal errors.
