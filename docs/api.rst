API Refrence
============

The following documentation defines all of the usable routes in the Zane API.

.. _auth:

Authorization
-------------
.. note::

    To authorize your requests you must supply your token with one of the following methods.

    * A query parameter named token with your token. ``?token=your_token``
    * An ``Authorization`` header containing your token. ``Authorization: your_token``

Image Manipulation
------------------

This section outlines all of the routes used for image manipulation.

Magic
`````
.. http:get:: /api/magic

    This returns a gif of the image being increasingly content aware scaled. Any image gets scaled to 256 x 256.

    **Example Request**:

    .. code-block:: rest

        GET /api/invert?url=https://via.placeholder.com/256.png?magnitude=0.6 HTTP/2
        Authorization: your_token
        Host: zane.ip-bash.com
        Accept: image/jpeg, image/png, image/gif

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/gif

    :statuscode 200: Manipulation was a success.
    :query magnitude: the magnitude of the content aware scaling. Must be between 0.1 and 2. Values outside of that range will be silently `clamped<https://en.wikipedia.org/wiki/Clamping_(graphics)>`_ into it.
    :query token: your api-key. (see :ref:`auth`)
    :resheader Authorization: your api-key. (see :ref:`auth`)
  
    
