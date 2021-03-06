.. currentmodule:: pandas

.. ipython:: python
   :suppress:

   import os
   import csv
   from pandas.compat import StringIO, BytesIO
   import pandas as pd
   ExcelWriter = pd.ExcelWriter

   import numpy as np
   np.random.seed(123456)
   randn = np.random.randn
   np.set_printoptions(precision=4, suppress=True)

   import matplotlib.pyplot as plt
   plt.close('all')

   import pandas.util.testing as tm
   pd.options.display.max_rows=15
   clipdf = pd.DataFrame({'A':[1,2,3],'B':[4,5,6],'C':['p','q','r']},
                         index=['x','y','z'])

.. _io.clipboard:

Clipboard
---------

A handy way to grab data is to use the ``read_clipboard`` method, which takes
the contents of the clipboard buffer and passes them to the ``read_table``
method. For instance, you can copy the following
text to the clipboard (CTRL-C on many operating systems):

.. code-block:: python

     A B C
   x 1 4 p
   y 2 5 q
   z 3 6 r

And then import the data directly to a DataFrame by calling:

.. code-block:: python

   clipdf = pd.read_clipboard()

.. ipython:: python

   clipdf

The ``to_clipboard`` method can be used to write the contents of a DataFrame to
the clipboard. Following which you can paste the clipboard contents into other
applications (CTRL-V on many operating systems). Here we illustrate writing a
DataFrame into clipboard and reading it back.

.. ipython:: python

    df = pd.DataFrame(randn(5,3))
    df
    df.to_clipboard()
    pd.read_clipboard()

We can see that we got the same content back, which we had earlier written to the clipboard.

.. note::

   You may need to install xclip or xsel (with gtk or PyQt4 modules) on Linux to use these methods.