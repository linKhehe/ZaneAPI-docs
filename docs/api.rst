API Refrence
============

The following documentation defines all of the usable routes in the Zane API.

.. warning::

  All routes use the base url of /api/v0/

Information Routes
------------------

This section outlines all of the routes used as information for the API.

.. http:get:: /status

    This returns the API's current status in json.
    It returns a status code and a message.
    The information will rarely change.

    **Example Request**:

    .. code-block:: rest

        GET /status HTTP

    **Example response**:

    .. code-block:: rest

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

This section outlines all of the routes used for image manipulation.


.. http:post:: /invert

    This returns an inverted version of the input image.
    If the image is larger than 512px in width or height,
    the image will be sampled down to 512px in the
    offending direction while preserving aspect ratio.

    **Example Request**:

    .. code-block:: rest

        POST /invert HTTP
        Accept: image/jpeg, image/png

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/png

        (image as bytes)

    :statuscode 200: Image manipulation is functioning correctly and has completed.
    :statuscode 404: The API functionality is currently disabled.
    :statuscode 500: The current endpoint is currently broken due to internal errors.


.. http:post:: /magic

    This returns a content aware scaled version of the input image.
    If the image is larger than 512px in width or height,
    the image will be sampled down to 512px in the
    offending direction while preserving aspect ratio.

    **Example Request**:

    .. code-block:: rest

        POST /magic HTTP
        Accept: image/jpeg, image/png

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/png

        (image as bytes)

    :statuscode 200: Image manipulation is functioning correctly and has completed.
    :statuscode 404: The API functionality is currently disabled.
    :statuscode 500: The current endpoint is currently broken due to internal errors.


.. http:post:: /deepfry

    This returns a deepfried version of the input image.
    If the image is larger than 512px in width or height,
    the image will be sampled down to 512px in the
    offending direction while preserving aspect ratio.

    **Example Request**:

    .. code-block:: rest

        POST /deepfry HTTP
        Accept: image/jpeg, image/png

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/png

        (image as bytes)

    :statuscode 200: Image manipulation is functioning correctly and has completed.
    :statuscode 404: The API functionality is currently disabled.
    :statuscode 500: The current endpoint is currently broken due to internal errors.


.. http:post:: /desat

    This returns a desaturated version of the input image.
    If the image is larger than 512px in width or height,
    the image will be sampled down to 512px in the
    offending direction while preserving aspect ratio.

    **Example Request**:

    .. code-block:: rest

        POST /desat HTTP
        Accept: image/jpeg, image/png

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/png

        (image as bytes)

    :statuscode 200: Image manipulation is functioning correctly and has completed.
    :statuscode 404: The API functionality is currently disabled.
    :statuscode 500: The current endpoint is currently broken due to internal errors.


.. http:post:: /noise

    This returns a noisy version of the input image.
    If the image is larger than 512px in width or height,
    the image will be sampled down to 512px in the
    offending direction while preserving aspect ratio.

    **Example Request**:

    .. code-block:: rest

        POST /noise HTTP
        Accept: image/jpeg, image/png

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/png

        (image as bytes)

    :statuscode 200: Image manipulation is functioning correctly and has completed.
    :statuscode 404: The API functionality is currently disabled.
    :statuscode 500: The current endpoint is currently broken due to internal errors.


.. http:post:: /color

    This returns a differently colored version of the input image.
    If the image is larger than 512px in width or height,
    the image will be sampled down to 512px in the
    offending direction while preserving aspect ratio.

    The color arg is parsed by wand.color.Color and can use
    any of the listed formats on `this page`__.

    .. __: https://imagemagick.org/script/color.php

    **Example Request**:

    .. code-block:: rest

        POST /color?color=blue HTTP
        Accept: image/jpeg, image/png

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/png

        (image as bytes)

    :statuscode 200: Image manipulation is functioning correctly and has completed.
    :statuscode 404: The API functionality is currently disabled.
    :statuscode 500: The current endpoint is currently broken due to internal errors.


.. http:post:: /sat

    This returns a saturated version of the input image.
    If the image is larger than 512px in width or height,
    the image will be sampled down to 512px in the
    offending direction while preserving aspect ratio.

    **Example Request**:

    .. code-block:: rest

        POST /sat HTTP
        Accept: image/jpeg, image/png

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/png

        (image as bytes)

    :statuscode 200: Image manipulation is functioning correctly and has completed.
    :statuscode 404: The API functionality is currently disabled.
    :statuscode 500: The current endpoint is currently broken due to internal errors.


.. http:post:: /arc

    This returns a 360 degree projection of the input image.
    If the image is larger than 512px in width or height,
    the image will be sampled down to 512px in the
    offending direction while preserving aspect ratio.

    **Example Request**:

    .. code-block:: rest

        POST /arc HTTP
        Accept: image/jpeg, image/png

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/png

        (image as bytes)

    :statuscode 200: Image manipulation is functioning correctly and has completed.
    :statuscode 404: The API functionality is currently disabled.
    :statuscode 500: The current endpoint is currently broken due to internal errors.


.. http:post:: /concave

    This returns a concave version of the input image.
    If the image is larger than 512px in width or height,
    the image will be sampled down to 512px in the
    offending direction while preserving aspect ratio.

    **Example Request**:

    .. code-block:: rest

        POST /concave HTTP
        Accept: image/jpeg, image/png

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/png

        (image as bytes)

    :statuscode 200: Image manipulation is functioning correctly and has completed.
    :statuscode 404: The API functionality is currently disabled.
    :statuscode 500: The current endpoint is currently broken due to internal errors.


.. http:post:: /convex

    This returns a convex version of the input image.
    If the image is larger than 512px in width or height,
    the image will be sampled down to 512px in the
    offending direction while preserving aspect ratio.

    **Example Request**:

    .. code-block:: rest

        POST /convex HTTP
        Accept: image/jpeg, image/png

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/png

        (image as bytes)

    :statuscode 200: Image manipulation is functioning correctly and has completed.
    :statuscode 404: The API functionality is currently disabled.
    :statuscode 500: The current endpoint is currently broken due to internal errors.


.. http:post:: /floor

    This returns a tiled floor textured with the input image.
    If the image is larger than 128px in width or height,
    the image will be sampled down to 128px in the
    offending direction while preserving aspect ratio.

    **Example Request**:

    .. code-block:: rest

        POST /floor HTTP
        Accept: image/jpeg, image/png

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/png

        (image as bytes)

    :statuscode 200: Image manipulation is functioning correctly and has completed.
    :statuscode 404: The API functionality is currently disabled.
    :statuscode 500: The current endpoint is currently broken due to internal errors.


.. http:post:: /blur

    This returns a blurred of the input image.
    If the image is larger than 512px in width or height,
    the image will be sampled down to 512px in the
    offending direction while preserving aspect ratio.

    **Example Request**:

    .. code-block:: rest

        POST /blur HTTP
        Accept: image/jpeg, image/png

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/png

        (image as bytes)

    :statuscode 200: Image manipulation is functioning correctly and has completed.
    :statuscode 404: The API functionality is currently disabled.
    :statuscode 500: The current endpoint is currently broken due to internal errors.


.. http:post:: /vaporwave

    This returns a vaporwave version of the input image.
    If the image is larger than 512px in width or height,
    the image will be sampled down to 512px in the
    offending direction while preserving aspect ratio.

    **Example Request**:

    .. code-block:: rest

        POST /vaporwave HTTP
        Accept: image/jpeg, image/png

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/png

        (image as bytes)

    :statuscode 200: Image manipulation is functioning correctly and has completed.
    :statuscode 404: The API functionality is currently disabled.
    :statuscode 500: The current endpoint is currently broken due to internal errors.


.. http:post:: /emboss

    This returns an embossed version of the input image.
    If the image is larger than 512px in width or height,
    the image will be sampled down to 512px in the
    offending direction while preserving aspect ratio.

    **Example Request**:

    .. code-block:: rest

        POST /emboss HTTP
        Accept: image/jpeg, image/png

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/png

        (image as bytes)

    :statuscode 200: Image manipulation is functioning correctly and has completed.
    :statuscode 404: The API functionality is currently disabled.
    :statuscode 500: The current endpoint is currently broken due to internal errors.


.. http:post:: /shade

    This returns a shaded of the input image.
    If the image is larger than 512px in width or height,
    the image will be sampled down to 512px in the
    offending direction while preserving aspect ratio.

    **Example Request**:

    .. code-block:: rest

        POST /shade HTTP
        Accept: image/jpeg, image/png

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/png

        (image as bytes)

    :statuscode 200: Image manipulation is functioning correctly and has completed.
    :statuscode 404: The API functionality is currently disabled.
    :statuscode 500: The current endpoint is currently broken due to internal errors.


.. http:post:: /bend

    This returns a curved (to 90 degrees) version of the input image.
    If the image is larger than 512px in width or height,
    the image will be sampled down to 512px in the
    offending direction while preserving aspect ratio.

    **Example Request**:

    .. code-block:: rest

        POST /bend HTTP
        Accept: image/jpeg, image/png

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/png

        (image as bytes)

    :statuscode 200: Image manipulation is functioning correctly and has completed.
    :statuscode 404: The API functionality is currently disabled.
    :statuscode 500: The current endpoint is currently broken due to internal errors.


.. http:post:: /posterize

    This returns a posterized of the input image.
    If the image is larger than 512px in width or height,
    the image will be sampled down to 512px in the
    offending direction while preserving aspect ratio.

    **Example Request**:

    .. code-block:: rest

        POST /posterize HTTP
        Accept: image/jpeg, image/png

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/png

        (image as bytes)

    :statuscode 200: Image manipulation is functioning correctly and has completed.
    :statuscode 404: The API functionality is currently disabled.
    :statuscode 500: The current endpoint is currently broken due to internal errors.


.. http:post:: /grayscale

    This returns a black and white of the input image.
    If the image is larger than 512px in width or height,
    the image will be sampled down to 512px in the
    offending direction while preserving aspect ratio.

    **Example Request**:

    .. code-block:: rest

        POST /grayscale HTTP
        Accept: image/jpeg, image/png

    **Example response**:

    .. code-block:: rest

        HTTP 200 OK
        Content-Type: image/png

        (image as bytes)

    :statuscode 200: Image manipulation is functioning correctly and has completed.
    :statuscode 404: The API functionality is currently disabled.
    :statuscode 500: The current endpoint is currently broken due to internal errors.
