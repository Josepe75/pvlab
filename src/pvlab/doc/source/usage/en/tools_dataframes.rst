======================
Sub-package dataframes
======================

.. py:module:: pvlab.dataframes

Provide tools to manage dataframes in the context of calibration.

It contains the following python modules:

Module dfdicts
^^^^^^^^^^^^^^

.. py:module:: pvlab.dataframes.dfdicts

   Perform type-conversion and *pretty-print* operations for dictionaries.

   It contains the following functions:


.. py:function:: dict_to_df(dictionary: dict, columns: list) -> pandas.core.frame.DataFrame

   Re-arrange a dictionary to become a pandas dataframe.

   It performs a type conversion of a dictionary (e.g. a dictionary that
   represents some kind of valid time intervals), returning a ``pandas`` DataFrame:

   When the correct parameters are provided, it **returns** a ``pandas.DataFrame``
   object.

.. code-block:: python
   :linenos:
   :lineno-start: 1
   :emphasize-lines: 4-6
   :caption: Example 1: correct fuctioning.
   :name: dict_to_df_correct
   dates = {'START_1': (2021,5,5,8,1,0), 'END_1': (2021,5,6,22,52,0)}
   columns = ['%Y', '%m', '%d', '%H', '%M', '%S']
   dict_to_df(dates, columns)
                 %Y  %m  %d  %H  %M  %S
   START_1  2021   5   5   8   1   0
   END_1    2021   5   6  22  52   0

Otherwise, a ``ValueError`` is raised when the length of ``columns``
does not match with the values of the given dictionary:

.. code-block:: python
   :linenos:
   :lineno-start: 7
   :emphasize-lines: 9-11
   :caption: Example 2: column shorter than expected.
   :name: dict_to_df_shorter
   columns = ['%Y', '%m', '%d', '%H', '%M']
   dict_to_df(dates, columns)
   Traceback (most recent call last):
       ...
   ValueError: Length of columns list is equal to 5, but has to be equal to 6.

.. code-block:: python
   :linenos:
   :lineno-start: 12
   :emphasize-lines: 1-2
   :caption: Example 3: column longer than expected.
   :name: dict_to_df_longer
   columns = ['%Y', '%m', '%d', '%H', '%M', '%S', '%mS']
   dict_to_df(dates, columns)
   Traceback (most recent call last):
       ...
   ValueError: Length of columns list is equal to 7, but has to be equal to 6.

.. py:function:: print_dict(dictionary: dict, columns: list, title: str = '') -> None
   
   *Prettyprint* a dictionary of dates, adding a title.
   It appears similar to ``dict_to_df``, but ``print_dict`` *just* print, do not
   return a ``pandas.DataFrame`` object (it returns ``None``):
   
.. code-block:: python   
   :linenos:
   :lineno-start: 1
   :emphasize-lines: 1-2
   :caption: Example 4: correct functioning.
   :name: print_dict
   dates = {'START_1': (2021,5,5,8,1,0), 'END_1': (2021,5,6,22,52,0)}
   columns = ['%Y', '%m', '%d', '%H', '%M', '%S']
   title = 'Valid time intervals'
   print_dict(dates, columns, title)
   Valid time intervals
   --------------------
               %Y  %m  %d  %H  %M  %S
   START_1  2021   5   5   8   1   0
   END_1    2021   5   6  22  52   0
   
