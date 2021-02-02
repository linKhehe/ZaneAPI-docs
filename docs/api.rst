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

        GET /api/magic?url=https://example.com/img.png&magnitude=0.6 HTTP/2
        Authorization: your_token
        Host: zane.ip-bash.com
        Accept: image/jpeg, image/png, image/gif

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/gif

    :statuscode 200: Manipulation was a success.
    :query string url: the url of the image you want to manipulate.
    :query float magnitude: the magnitude of the content aware scaling. Must be between 0.1 and 2. Values outside of that range will be silently `clamped <https://en.wikipedia.org/wiki/Clamping_(graphics)>`_ into it. (optional, default is 0.6)
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

.. note::
    This endpoint returns text. Not an image.

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

Deepfry
```````

.. http:get:: /api/deepfry

    Deepfry an image.

    **Example Request**:

    .. code-block:: rest

        GET /api/deepfry?url=https://example.com/img.png HTTP/2
        Authorization: your_token
        Host: zane.ip-bash.com
        Accept: image/jpeg, image/png, image/gif

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/png

    :statuscode 200: Manipulation was a success.
    :query string url: the url of the image you want to manipulate.
    :query string token: your api-key. (optional, see :ref:`auth`)
    :resheader Authorization: your api-key. (optional, see :ref:`auth`)
    
    
Dots
````

.. http:get:: /api/dots

    Recreate the image with overlapping black and white dots.

    **Example Request**:

    .. code-block:: rest

        GET /api/dots?url=https://example.com/img.png HTTP/2
        Authorization: your_token
        Host: zane.ip-bash.com
        Accept: image/jpeg, image/png, image/gif

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/png

    :statuscode 200: Manipulation was a success.
    :query string url: the url of the image you want to manipulate.
    :query string token: your api-key. (optional, see :ref:`auth`)
    :resheader Authorization: your api-key. (optional, see :ref:`auth`)
    
Jpeg
````

.. http:get:: /api/jpeg

    Compresses the image and strips it of any quality. Just like a JPEG.

    **Example Request**:

    .. code-block:: rest

        GET /api/jpeg?url=https://example.com/img.png HTTP/2
        Authorization: your_token
        Host: zane.ip-bash.com
        Accept: image/jpeg, image/png, image/gif

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/png

    :statuscode 200: Manipulation was a success.
    :query string url: the url of the image you want to manipulate.
    :query string token: your api-key. (optional, see :ref:`auth`)
    :resheader Authorization: your api-key. (optional, see :ref:`auth`)
    
Spread
``````

.. http:get:: /api/spread

    Animates spreading out all the pixels in the image giving a cool explosion-esque look.

    **Example Request**:

    .. code-block:: rest

        GET /api/spread?url=https://example.com/img.png HTTP/2
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
    
Cube
````

.. http:get:: /api/cube

    Makes a 3D looking cube out of the image.

    **Example Request**:

    .. code-block:: rest

        GET /api/cube?url=https://example.com/img.png HTTP/2
        Authorization: your_token
        Host: zane.ip-bash.com
        Accept: image/jpeg, image/png, image/gif

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/png

    :statuscode 200: Manipulation was a success.
    :query string url: the url of the image you want to manipulate.
    :query string token: your api-key. (optional, see :ref:`auth`)
    :resheader Authorization: your api-key. (optional, see :ref:`auth`)

Sort
````

.. http:get:: /api/sort

    Sort the pixels in the image.

    **Example Request**:

    .. code-block:: rest

        GET /api/sort?url=https://example.com/img.png HTTP/2
        Authorization: your_token
        Host: zane.ip-bash.com
        Accept: image/jpeg, image/png, image/gif

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/png

    :statuscode 200: Manipulation was a success.
    :query string url: the url of the image you want to manipulate.
    :query string token: your api-key. (optional, see :ref:`auth`)
    :resheader Authorization: your api-key. (optional, see :ref:`auth`)
    
Palette
```````

.. http:get:: /api/palette

    Image that takes up to 8 colors from the image and overlays their color and hex code to the side of the image.

    **Example Request**:

    .. code-block:: rest

        GET /api/palette?url=https://example.com/img.png HTTP/2
        Authorization: your_token
        Host: zane.ip-bash.com
        Accept: image/jpeg, image/png, image/gif

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/png

    :statuscode 200: Manipulation was a success.
    :query string url: the url of the image you want to manipulate.
    :query string token: your api-key. (optional, see :ref:`auth`)
    :resheader Authorization: your api-key. (optional, see :ref:`auth`)
    
Invert
``````

.. http:get:: /api/invert

    Negate the image.

    **Example Request**:

    .. code-block:: rest

        GET /api/invert?url=https://example.com/img.png HTTP/2
        Authorization: your_token
        Host: zane.ip-bash.com
        Accept: image/jpeg, image/png, image/gif

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/png

    :statuscode 200: Manipulation was a success.
    :query string url: the url of the image you want to manipulate.
    :query string token: your api-key. (optional, see :ref:`auth`)
    :resheader Authorization: your api-key. (optional, see :ref:`auth`)
    
Posterize
`````````

.. http:get:: /api/posterize

    `Posterize <https://en.wikipedia.org/wiki/Posterization>`_ the image.

    **Example Request**:

    .. code-block:: rest

        GET /api/posterize?url=https://example.com/img.png HTTP/2
        Authorization: your_token
        Host: zane.ip-bash.com
        Accept: image/jpeg, image/png, image/gif

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/png

    :statuscode 200: Manipulation was a success.
    :query string url: the url of the image you want to manipulate.
    :query string token: your api-key. (optional, see :ref:`auth`)
    :resheader Authorization: your api-key. (optional, see :ref:`auth`)
    
Grayscale
`````````

.. http:get:: /api/grayscale

    Convert the image to grayscale.

    **Example Request**:

    .. code-block:: rest

        GET /api/grayscale?url=https://example.com/img.png HTTP/2
        Authorization: your_token
        Host: zane.ip-bash.com
        Accept: image/jpeg, image/png, image/gif

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/png

    :statuscode 200: Manipulation was a success.
    :query string url: the url of the image you want to manipulate.
    :query string token: your api-key. (optional, see :ref:`auth`)
    :resheader Authorization: your api-key. (optional, see :ref:`auth`)
    
Pixelate
````````

.. http:get:: /api/invert

    Negate the image.

    **Example Request**:

    .. code-block:: rest

        GET /api/invert?url=https://example.com/img.png&scale=0.3 HTTP/2
        Authorization: your_token
        Host: zane.ip-bash.com
        Accept: image/jpeg, image/png, image/gif

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/png

    :statuscode 200: Manipulation was a success.
    :query string url: the url of the image you want to manipulate.
    :query float scale: the scale to pixelate the image with. Lower is more pixelated. Silently `clamped <https://en.wikipedia.org/wiki/Clamping_(graphics)>`_ between 0.1 and 1. (optional, default is 0.3)
    :query string token: your api-key. (optional, see :ref:`auth`)
    :resheader Authorization: your api-key. (optional, see :ref:`auth`)
    
    
Swirl
`````

.. http:get:: /api/swirl

    Animate a swirling effect on the image.

    **Example Request**:

    .. code-block:: rest

        GET /api/swirl?url=https://example.com/img.png&angle=280 HTTP/2
        Authorization: your_token
        Host: zane.ip-bash.com
        Accept: image/jpeg, image/png, image/gif

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/gif

    :statuscode 200: Manipulation was a success.
    :query string url: the url of the image you want to manipulate.
    :query int angle: the max swirl angle in degrees. Not clamped. (optional, default is 280)
    :query string token: your api-key. (optional, see :ref:`auth`)
    :resheader Authorization: your api-key. (optional, see :ref:`auth`)
    
Sobel
`````

.. http:get:: /api/sobel

    Apply a sobel filter to the image.

    **Example Request**:

    .. code-block:: rest

        GET /api/sobel?url=https://example.com/img.png HTTP/2
        Authorization: your_token
        Host: zane.ip-bash.com
        Accept: image/jpeg, image/png, image/gif

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/png

    :statuscode 200: Manipulation was a success.
    :query string url: the url of the image you want to manipulate.
    :query string token: your api-key. (optional, see :ref:`auth`)
    :resheader Authorization: your api-key. (optional, see :ref:`auth`)
