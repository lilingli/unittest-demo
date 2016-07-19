======================================
The Project Structure of unittest demo
======================================

Introduction
============

This document describes the structure of this project, and the steps to setup 
the structure.

2 documents are referred to setup the project structure:

- `Structuring Your Project
  <http://docs.python-guide.org/en/latest/writing/structure/>`_
- `Python Packaging User Guide <https://packaging.python.org/>`_

Project Structure
=================

The project contains the following directories:

- Home directory
- ``doc``
- ``unittest_demo``

Then those directories will be described in details.

Home directory
==============

Home directory names unittest-demo as the project name, and contains everything
belonging to the project. It is also the top directory of the git respository.

Beside the 1st level diretories, home directory contains the following resources
shared across the whole project:

- ``.gitignore``:
    The file contains the file or directory patterns which should not be added
    into the git repository, such as temporary files, generated files, local
    environment configuration files, etc.

- ``LICENSE``:
    The license information of the project.

- ``README.rst``:
    The brief introduction of the project.

doc directory
=============

This directory contains the project documentation resources following 
Sphinx_ approach.

The structure and the configuration and script files are generated with Sphinx
tool within ``doc`` directory ::

  sphinx-quickstart

The Sphinx guidance can be found in `Sphinx Tutorial
<http://www.sphinx-doc.org/en/stable/tutorial.html>`_.

The ``doc`` directory contains the following resources

- ``source``:
    This directory contains the documentation resource files, in
    `reStructuredTest <http://docutils.sourceforge.net/rst.html>`_ format. All
    of the project documents should be added into this directory or its
    subdirectories.
- ``build``:
    The Sphinx_ output documents generated from the rst files within
    ``doc/source`` directory are stored in ``build`` directory.
    This directory and its content is generated with ``make`` command in Lunix
    or ``make.bat`` in Windows within ``doc`` directory, and ignored by Git.
- ``Makefile``:
    The build script in Linux to call Sphinx_ to generate output documents from
    rst resource files within ``doc/source`` directory.
- ``make.bat``:
    The ``Makefile`` used for Windows platform. When the document generation
    process is changed, the both 2 scripts should be changed.

unittest_demo
=============

This directory contains the top module of the project source code. The code to
be tested by the demo unit test is stored in this directory the same as the
normal projects.

The unit test source code is contained within the ``unittest_demo/test``
subdirectory. Actually it is not a good practise as it is tricky to separate the
system code from the test code. Ideally, the test code should not be deployed or
installed with the system code, so it would be better to have 2 ditectories 
at the same level and contain system code and unit test code separately. 
However, it looks like it is the common approache to store the 2 parts of the
code together, so this approache is still followed here.

.. _Sphinx: http://www.sphinx-doc.org/en/stable