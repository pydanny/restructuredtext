============================================
Testing your Documentation
============================================

If you want to confirm that your docs build successfully, you add this to your tox.ini file:

.. code-block:: ini

    [tox]
    envlist = sphinx, readme

    [testenv:sphinx]
    deps =
        Sphinx
    commands =
        make --directory=docs clean html
    whitelist_externals =
        make

    [testenv:readme]
    deps =
        docutils
        pygments
    commands =
        rst2html.py --exit-status=2 README.rst /tmp/README.html
        rst2html.py --exit-status=2 CONTRIBUTING.rst /tmp/CONTRIBUTING.html
        
TODO: Explain in depth what this actually does.

TODO: Explain what tox is.