Release 0.1.0.dev7
------------------

1. Added two new functions in sub-package ``io``:
   #. ``set_channels(numbers: Iterable[int], names: Iterable[str], nameafter: bool = True) -> Iterable[str])``.
   #. ``set_channels_grouped(numbergroups: Iterable[Iterable[int]], namegroups: Iterable[Iterable[str]], nameafter: Iterable[bool] = True, unify: bool = True, init_channels: list = []) -> Iterable[str]``.

2. New functions are intended to facilitate the import of data files. Function ``set_channels`` generates a list of *titles* or *channel headings* from a list of channel numbers and a list of common names, in such a way that the creation of strings like: ['101(Time stamp)', '101(VDC)', ..., 'xxx(Time stamp)', 'xxx(VDC)'], can be done automatically.
