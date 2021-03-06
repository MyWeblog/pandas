.. _10min:

********************
10 Minutes to pandas
********************

This is a short introduction to pandas, geared mainly for new users.
You can see more complex recipes in the :ref:`Cookbook<cookbook>`

.. toctree::
    :maxdepth: 1
    :caption: Contents
    :name: 10min

    10min1
    10min2
    10min3
    10min4
    10min5
    10min6
    10min7
    10min8
    10min9
    10min10
    10min11
    10min12
    10min13

.. currentmodule:: pandas

.. ipython:: python

   import numpy as np
   import pandas as pd
   import os
   np.random.seed(123456)
   np.set_printoptions(precision=4, suppress=True)
   import matplotlib
   matplotlib.style.use('ggplot')
   import matplotlib.pyplot as plt
   pd.options.display.max_rows = 8