==================
python-duckduckgo
==================

A Python library for querying the Duck Duck Go API.

Copyright Michael Stephens <me@mikej.st>, released under a BSD-style license.

Source: http://github.com/mikejs/python-duckduckgo

Installation
============

To install run

    ``python setup.py install``

Usage
=====
    >>> # First we want to import the duckduckgo API
    >>> import duckduckgo
    >>> # Then we are assigning 'r' to the search Duck Duck Go 
    >>> r = duckduckgo.query('Duck Duck Go')
    >>> r.type
    'answer'
    >>> # Since we are accessing the results part of the Duck Duck Go API, if we set the element to 0 we can see this: 
    >>> r.results[0].text
    'Official site'
    >>> r.results[0].url
    'http://duckduckgo.com/'
    >>> r.abstract.url
    'http://en.wikipedia.org/wiki/Duck_Duck_Go'
    >>> r.abstract.source
    'Wikipedia'
    >>> # Now we are going to access the search Python
    >>> r = duckduckgo.query('Python')
    >>> #In the API, we are using teh disambiguation type, so this is what is returned 
    >>> r.type
    'disambiguation'
    >>> #Again, we can see the text involved in element 6 of the related API 
    >>> r.related[6].text
    'Python (programming language), a computer programming language'
    >>> r.related[6].url
    'http://duckduckgo.com/Python_(programming_language)'  
    >>> #Searching for 1 + 1 : 
    >>> r = duckduckgo.query('1 + 1')
    >>> r.type
    'nothing'
    >>> r.answer.text
    '1 + 1 = 2'
    >>> r.answer.type
    'calc'
