Software Engineering Techniques
===============================

9 July 2018

pytests
-------

Legitimate to have a pytest that doesn't have assertions because at the least
it will show that the code did not have a syntax bug.

Good idea to keep logic code separated from command line interface ("cli") code.

`click` is good for complicated arg parsing with sub-commands

cProfile
---------

Use to analyze time spent in different functions in code.

	python -m cProfile -o profile_data cli.py ./data/sf_restaurant_scores_full.csv 5 2018

This cannot be used to analyze code that hooks into C, Fortran, etc. Only can see into Python.

For memory profiling, use a thing called "memory profiler".

Use this in notebook with `%prun` put at top of cell of code.

snakeviz
--------

Creates visuale representation of time spent in each function of code:

	snakeviz profile_data

In the notebook, `%snakeviz`

Packaging
---------

Don't need empty `__init__.py` anymore in Python 3.3+.

Anything submitted to pip was packaged using `setuptools`.

To package to pip:

	setup.py dist

This will make a zip file. Could also just give it to someone. 

Or can use `wheel`, which will generate a `whl` file of your compilation. You can give this to
someone with the same system as you, and it will install to their system super fast because
it is already compiled.