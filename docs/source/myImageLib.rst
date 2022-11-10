myImageLib
==========

A library that hosts general image analysis tools.

File reading, image processing and plotting
-------------------------------------------

.. py:function:: myImageLib.dirrec(path, filename)




.. py:function:: myImageLib.to8bit(img)


.. py:function:: myImageLib.bpass(img, low, high)



.. py:function:: myImageLib.bestcolor(n)



.. py:function:: myImageLib.wowcolor(n)



.. py:function:: myImageLib.readdata(folder, ext="csv")

  Wrapper of :py:func:`dirrec`, but easier to use when reading one type of files in a given folder. Instead of returning a list of directories as :py:func:`dirrec` does, :py:func:`readdata` puts the file names and corresponding full directories in a :code:`pandas.DataFrame`. The table will be sorted by the file names (strings), so the order would likely be correct. In the worst case, it is still easier to resort the :code:`pandas.DataFrame`, compared to the list of strings returned by :py:func:`dirrec`.

  :param folder: the folder to read files from
  :type folder: str
  :param ext: optional param, default to "csv", specifies the extension of files to be read
  :type ext: str
  :return: a 2-column table containing file names and the corresponding full directories
  :rtype: pandas.DataFrame

.. py:function:: myImageLib.show_progress(progress, label='', bar_length=60)

  Display a progress bar in command line environment, which looks like

  .. code-block:: console

    label [##############-----------] 62%

  This is a useful tool for tracking work progress in a batch processing task on a server.

  :param progress: the progress of the work. It is a number between 0 and 1, where 0 is start and 1 is finish
  :type progress: float
  :param label: a string to put before the progress bar. It can be the name of the work, or the actual number of files that have been processed, and so on. Default to :code:`''`.
  :type label: str
  :param bar_length: length of the progress bar, in the unit of characters. Default to :code:`60`.
  :type bar_length: int
  :return: None
