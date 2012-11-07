=========================================
Python bindings for The Best Spinner API.
=========================================

`The Best Spinner <http://thebestspinner.com/>`_ is an online
service for spinning text (synonym substitution) that creates unique version(s)
of existing text. This package provides a way to easily interact with
The Best Spinner API.

* `Source code @ GitHub <https://github.com/matejc/tbsab>`_


Install within virtualenv
=========================

.. sourcecode:: bash

    $ virtualenv foo
    $ cd foo
    $ git clone https://github.com/matejc/tbsab
    $ bin/pip install tbsab/

    # running tests:
    $ bin/pip install unittest2 mock
    $ bin/python -m unittest discover -s tbsab/src/tbsab/tests


Buildout
========

.. sourcecode:: bash

    $ git clone https://github.com/matejc/tbsab
    $ cd tbsab
    $ python bootstrap.py
    $ bin/buildout

    # running tests:
    $ bin/py -m unittest discover -s src/tbsab/tests

    # check code for imperfections
    $ bin/vvv src/tbsab


Usage
=====

.. sourcecode:: python

    >>> original_text = "This is the text we want to spin"
    >>> import tbs
    >>> tbs = tbs.Api('your_username', 'your_password')
    >>> spin_text = tbs.identifySynonyms(text)
    >>> print spin_text
    u"{This is|This really is|That is|This can be} some text that we'd {like to|prefer to|want to|love to} spin"
    >>> tbs.randomSpin(spin_text)
    u"This really is some text that we'd love to spin"

