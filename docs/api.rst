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

    .. code-block:: html

        GET /status HTTP

    **Example response**:

    .. code-block:: html

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
    the image will be sampled down to that 512px in the
    offending direction while preserving aspect ratio.

    **Example Request**:

    .. code-block:: html

        POST /invert HTTP
        Accept: image/jpeg, image/png

    **Example response**:

    .. code-block:: html

        HTTP 200 OK
        Content-Type: image/png

        (image as bytes)

    :statuscode 200: Image manipulation is functioning correctly and has completed.
    :statuscode 404: The API functionality is currently disabled.
    :statuscode 500: The current endpoint is currently broken due to internal errors.


.. http:post:: /magic

    This returns a content aware scaled version of the input image.
    If the image is larger than 512px in width or height,
    the image will be sampled down to that 512px in the
    offending direction while preserving aspect ratio.

    **Example Request**:

    .. code-block:: html

        POST /magic HTTP
        Accept: image/jpeg, image/png

    **Example response**:

    .. code-block:: html

        HTTP 200 OK
        Content-Type: image/png

        (image as bytes)

    :statuscode 200: Image manipulation is functioning correctly and has completed.
    :statuscode 404: The API functionality is currently disabled.
    :statuscode 500: The current endpoint is currently broken due to internal errors.


.. http:post:: /deepfry

    This returns a deepfried version of the input image.
    If the image is larger than 512px in width or height,
    the image will be sampled down to that 512px in the
    offending direction while preserving aspect ratio.

    **Example Request**:

    .. code-block:: html

        POST /deepfry HTTP
        Accept: image/jpeg, image/png

    **Example response**:

    .. code-block:: html

        HTTP 200 OK
        Content-Type: image/png

        (image as bytes)

    :statuscode 200: Image manipulation is functioning correctly and has completed.
    :statuscode 404: The API functionality is currently disabled.
    :statuscode 500: The current endpoint is currently broken due to internal errors.


.. http:post:: /desat

    This returns a desaturated version of the input image.
    If the image is larger than 512px in width or height,
    the image will be sampled down to that 512px in the
    offending direction while preserving aspect ratio.

    **Example Request**:

    .. code-block:: html

        POST /desat HTTP
        Accept: image/jpeg, image/png

    **Example response**:

    .. code-block:: html

        HTTP 200 OK
        Content-Type: image/png

        (image as bytes)

    :statuscode 200: Image manipulation is functioning correctly and has completed.
    :statuscode 404: The API functionality is currently disabled.
    :statuscode 500: The current endpoint is currently broken due to internal errors.


.. http:post:: /noise

    This returns a noisy version of the input image.
    If the image is larger than 512px in width or height,
    the image will be sampled down to that 512px in the
    offending direction while preserving aspect ratio.

    **Example Request**:

    .. code-block:: html

        POST /noise HTTP
        Accept: image/jpeg, image/png

    **Example response**:

    .. code-block:: html

        HTTP 200 OK
        Content-Type: image/png

        (image as bytes)

    :statuscode 200: Image manipulation is functioning correctly and has completed.
    :statuscode 404: The API functionality is currently disabled.
    :statuscode 500: The current endpoint is currently broken due to internal errors.


.. http:post:: /color

    This returns a differently colored version of the input image.
    If the image is larger than 512px in width or height,
    the image will be sampled down to that 512px in the
    offending direction while preserving aspect ratio.

    The color arg is parsed by wand.color.Color and can use
    any of the listed formats on `this page`__.

    .. __: https://imagemagick.org/script/color.php

    **Example Request**:

    .. code-block:: html

        POST /color?color=blue HTTP
        Accept: image/jpeg, image/png

    **Example response**:

    .. code-block:: html

        HTTP 200 OK
        Content-Type: image/png

        (image as bytes)

    :statuscode 200: Image manipulation is functioning correctly and has completed.
    :statuscode 404: The API functionality is currently disabled.
    :statuscode 500: The current endpoint is currently broken due to internal errors.
