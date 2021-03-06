# py-gdx

## 1. What?

py-gdx is a small set of Python utilities for manipulating [GAMS](http://www.gams.com) GDX files.
It uses the Python bindings available in recent (as of 2011) versions of GAMS.
py-gdx in released under the [MIT Licence](http://www.opensource.org/licenses/mit-license.php).

There are several example scripts:

- `gdx_insert_csv.py` inserts or replaces variables in the GDX file with data in a CSV file.  If required it can create a new GDX file from scratch.
- `gdx_extract_csv.py` produces a CSV report of parameter and variable values in one or more GDX files.  If parameter domains are missing from the GDX file, it guesses them.  It can act as if several GDX files were one, or it can compare the same parameters in several GDX files.  It can export a selected set of parameters, it can export all parameters that are defined over a selected set of domains, or it can export all parameters and variables in a GDX file.  The csv files it writes are readable by `gdx_insert_csv.py`, so you can export an entire GDX file to CSV, edit it, and rebuild a new copy of the GDX.
- `gdx_merge.py` merges two GDX files *without* creating an extra index as the standard GDX merge tool does.

In all cases use `python gdx_<example>.py --help` to find out how to use them.

The above scripts use `gdxdict.py` to do their magic.  `gdxdict.py` loads a
GDX file into an object that acts much like Python a dictionary, and can write a GDX file from a such a dictionary.

At the moment, documentation of `gdxdict.py` is limited to the example files.


## 2. Requirements

- a "recent" version of GAMS or at least the GDX library - GAMS 23.2 does not have Python bindings, 23.7 does.
- Python 2.6 - the GDX bindings do not seem to support Python 3 or 2.7.
- you must have followed the installation instructions for Python in `<gams-dir>\apifiles\readme.txt`
  - make sure you have the right bindings for your Python version
  - make sure that the relevant files (`gdxcc.[so,dll]` and
    `gdxcc.py` are either installed in your python `site-packages` directory
    or the path to the files is in your PythonPath (on Windows they'll be
    somewhere like `C:\Program Files\GAMS23.7\apifiles\gdx`)

In short, if `python <gams-dir>\apifiles\Python\example1.py <gams-dir>`
doesn't work, then py-gdx won't work either.  You need to install the
GAMS/Python bindings correctly.
Either ask GAMS for help, or use Lua.


## 3. Who?

py-gdx was developed by [Incremental](http://www.incremental.co.nz/)
with support from the [Electricity Authority](http://www.ea.govt.nz/)
You can contact us at <info@incremental.co.nz>.
