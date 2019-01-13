Examples
========

This page contains examples on how to use the API.

Python
------

**AioHTTP/Wand Example**:
    .. code-block:: python

        # in a coroutine

        import io

        # this example will be using wand but you can use any
        # image manipulation library
        from wand.image import Image
        # this example will also be using aiohttp but you can use
        # any library
        import aiohttp

        # start a session
        session = aiohttp.ClientSession()

        with Image(filename="test.png") as image:
            # Save the image to a bytes buffer
            bytes_io = io.BytesIO()
            image_data = image.save(bytes_io)
            bytes_io.seek(0)

            # post the bytes buffer to the invert endpoint
            async with session.post("http://base_url.com/api/v0/invert", data=bytes_io) as resp:
                # this is when you get the image data back. from here you can do whatever with it
                # in this example we are going to save it back to test.png
                with Image(blob=(await resp.read())) as output_image:
                    output_image.save("test.png")
