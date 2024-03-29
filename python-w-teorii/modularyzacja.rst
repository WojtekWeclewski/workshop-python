******************************************
Modularyzacja, wersjonowanie i dystrybucja
******************************************

Modularyzacja
=============

Plik ``__init__.py``
--------------------

Linia ``if __name__ == '__main__'``
-----------------------------------

Importowanie względne ``from . import *``
-----------------------------------------

Konwencja nazewnicza - ``main.py``
----------------------------------


Paczkowanie
===========

``setup.py``
------------

.. code:: python

    import sys
    from setuptools import find_packages
    from setuptools import setup


    assert sys.version_info >= (3, 4), 'Python 3.4+ required.'

    setup(
        name='atlassian-python-api',
        description='Python Atlassian REST API Wrapper',
        long_description='Python Atlassian REST API Wrapper',
        license='Apache License 2.0',
        version='0.14.0',
        download_url='https://github.com/MattAgile/atlassian-python-api',

        author='Matt Harasymczuk',
        author_email='code@mattagile.com',
        url='http://mattagile.com/',

        packages=find_packages(),
        package_data={'': ['LICENSE', 'README.rst'], 'atlassian': ['*.py']},
        package_dir={'atlassian': 'atlassian'},
        include_package_data=True,

        zip_safe=False,
        install_requires=['requests==2.7.0'],
        platforms='Platform Independent',

        classifiers=[
            'Development Status :: 4 - Beta',
            'Environment :: Web Environment',
            'Intended Audience :: Developers',
            'Intended Audience :: System Administrators',
            'License :: OSI Approved :: Apache Software License',
            'Natural Language :: English',
            'Operating System :: OS Independent',
            'Operating System :: POSIX',
            'Operating System :: MacOS :: MacOS X',
            'Operating System :: Microsoft :: Windows',
            'Programming Language :: Python',
            'Programming Language :: Python :: 3',
            'Programming Language :: Python :: 3.0',
            'Programming Language :: Python :: 3.1',
            'Programming Language :: Python :: 3.2',
            'Programming Language :: Python :: 3.3',
            'Programming Language :: Python :: 3.4',
            'Topic :: Internet',
            'Topic :: Internet :: WWW/HTTP',
            'Topic :: Internet :: WWW/HTTP :: Dynamic Content',
            'Topic :: Software Development :: Libraries :: Python Modules',
            'Topic :: Software Development :: Libraries :: Application Frameworks']
    )

``setup.cfg``
-------------

.. code:: ini

    [pep8]
    max-line-length = 939
    ignore = E402,W391

``python setup.py sdist upload``
--------------------------------

``pip search``
--------------

``pip install``
---------------

``pip install -r requirements.txt``
-----------------------------------

``requirements.txt`` a ``setup.py``
-----------------------------------

``wheel``
---------

``distutils`` i ``setuptools``
------------------------------

Przyszłość paczkowania
----------------------

* https://www.youtube.com/watch?v=jOiAp3wtx18
* https://www.youtube.com/watch?v=Oc9khbXBes8