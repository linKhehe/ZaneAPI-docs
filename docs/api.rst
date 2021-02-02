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

        GET /api/magic?url=https://example.com/img.png?magnitude=0.6 HTTP/2
        Authorization: your_token
        Host: zane.ip-bash.com
        Accept: image/jpeg, image/png, image/gif

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/gif

    :statuscode 200: Manipulation was a success.
    :query string url: the url of the image you want to manipulate.
    :query float magnitude: the magnitude of the content aware scaling. Must be between 0.1 and 2. Values outside of that range will be silently `clamped <https://en.wikipedia.org/wiki/Clamping_(graphics)>`_ into it. (optional)
    :query string token: your api-key. (optional, see :ref:`auth`)
    :resheader Authorization: your api-key. (optional, see :ref:`auth`)
  
Floor
`````
.. warning::
    This endpoint is very slow. Use with caution.

.. http:get:: /api/floor

    This returns a gif of the image being bent like a bendy floor? You just have to see it for yourself. Any image gets scaled to 256 x 256.

    **Example Request**:

    .. code-block:: rest

        GET /api/floor?url=https://example.com/img.png HTTP/2
        Authorization: your_token
        Host: zane.ip-bash.com
        Accept: image/jpeg, image/png, image/gif

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/gif

    :statuscode 200: Manipulation was a success.
    :query string url: the url of the image you want to manipulate.
    :query string token: your api-key. (optional, see :ref:`auth`)
    :resheader Authorization: your api-key. (optional, see :ref:`auth`)
    

Braille
```````

.. http:get:: /api/braille

    This returns the image (scaled into a square) made with dithering braille characters with an effective resolution of 114 x 136 however you can input an image of any size.

    **Example Request**:

    .. code-block:: rest

        GET /api/braille?url=https://example.com/img.png HTTP/2
        Authorization: your_token
        Host: zane.ip-bash.com
        Accept: image/jpeg, image/png, image/gif

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: text/html; charset=utf-8

    :statuscode 200: Manipulation was a success.
    :query string url: the url of the image you want to manipulate.
    :query string token: your api-key. (optional, see :ref:`auth`)
    :resheader Authorization: your api-key. (optional, see :ref:`auth`)
