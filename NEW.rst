Release 0.1.0.dev7
------------------

#. Added two new functions in sub-package ``io``, intended to facilitate the import of data files:

   #. ``set_channels(numbers: Iterable[int], names: Iterable[str], nameafter: bool = True) -> Iterable[str])``.
   
   #. ``set_channels_grouped(numbergroups: Iterable[Iterable[int]], namegroups: Iterable[Iterable[str]], nameafter: Iterable[bool] = True, unify: bool = True, init_channels: list = []) -> Iterable[str]``.

#. Function ``set_channels`` generates a list of *titles* or *channel headings* from a list of channel numbers and a list of common names, in such a way that the creation of lists like: ['101(Time stamp)', '101(VDC)', ..., 'xxx(Time stamp)', 'xxx(VDC)'], can be done automatically, improving performance and reducing typing errors. See documentation of `set_channels`_ fuction for further information and examples.

#. Function ``set_channels_grouped``calls to function ``set_channels`` recursively, in such a way that it generates a unique ``list`` of strings (or a ``list`` of lists, if the ``unify`` argument is set to ``False``), containing diferent type of headings. See documentation of `set_channels_grouped`_ for further information.

.. _set_channels: https://pvlab.readthedocs.io/en/latest/usage/en/tools_io.html#function-set-channels

.. _set_channels_grouped: https://pvlab.readthedocs.io/en/latest/usage/en/tools_io.html#function-set-channels-grouped
