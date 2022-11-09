myImageLib
==========

A library that hosts general image analysis tools.

File reading, image processing and plotting
-------------------------------------------

.. py:function:: myImageLib.dirrec(path, filename)

  Recursively look for all the directories of files with name *filename*.

 :param path: the directory where you want to look for files.
 :type path: str
 :param filename: name of the files you want to look for.
 :type filename: str
 :return: a list of full directories of files with name *filename*
 :rtype: list[str]

 .. note::

   *filename* can be partially specified, e.g. '\*.py' to search for all the
       .py files or 'track\*' to search for all files starting with 'track'.

.. py:function:: myImageLib.to8bit(img)

  Enhance contrast and convert to 8-bit.

  :param img: mono image of any dtype
  :type img: 2d array
  :return: 8-bit image
  :rtype: uint8 2d array

.. py:function:: myImageLib.bpass(img, low, high)

  Apply bandpass filter on images. Useful when raw images have long wavelength intensity gradient.

  :param img: 8-bit image
  :type img: 2d array
  :param low: lower limit wavelength
  :type low: int
  :param high: upper limit wavelength
  :type high: int
  :return: processed image with low and high wavelength signals filtered
  :rtype: 2d array

.. py:function:: myImageLib.bestcolor(n)

  Default plot color scheme of Matplotlib and Matlab, "tab10" colormap

.. py:function:: myImageLib.wowcolor(n)

  WOW class color scheme, used in my density fluctuations paper. I used to think these colors are aesthetically pleasing, but now I feel they are too saturated and cause eye fatigue easily. Therefore I would avoid using these colors in future publications.

.. py:function:: myImageLib.readdata(folder, ext="csv")

  Wrapper of :py:func:`dirrec`, return DataFrame of ("Name", "Dir")

.. py:function:: myImageLib.show_progress(progress, label='', bar_length=60)

  Show progress in command line as [##############-----------] xx%. This is a useful tool for batch processing on a server.
