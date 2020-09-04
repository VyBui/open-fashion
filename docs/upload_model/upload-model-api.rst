Importing Libraries Documentation
============================

.. meta::
   :description lang=en: Import your existing technical documentation from version control into Read the Docs.


To import a public documentation repository, visit your `Read the Docs dashboard`_ and click Import_.
For private repositories, please use :doc:`Read the Docs for Business </commercial/index>`.


If you have :doc:`connected your Read the Docs account <../connected-accounts>` to GitHub, Bitbucket, or GitLab,
you will see a list of your repositories that we are able to import.
To import one of these projects, just click the import
icon next to the repository you'd like to import. This will bring up a form that
is already filled with your project's information. Feel free to edit any of
these properties, and then click **Next** to
:ref:`build your documentation <intro/import-guide:Building your documentation>`.

.. _Read the Docs dashboard: https://readthedocs.org/dashboard
.. _Import: https://readthedocs.org/dashboard/import


.. figure:: ../_static/images/first-steps/import-a-repository.png
    :align: right
    :figwidth: 300px
    :target: ../_static/images/first-steps/import-a-repository.png

    Importing a repository


Manually import your docs
-------------------------

If you do not have a connected account, you will need to select **Import Manually**
and enter the information for your repository yourself. You will also need to
manually configure the webhook for your repository as well. When importing your
project, you will be asked for the repository URL, along with some other
information for your new project. The URL is normally the URL or path name you'd
use to checkout, clone, or branch your repository. Some examples:

* Git: ``https://github.com/ericholscher/django-kong.git``
* Mercurial: ``https://bitbucket.org/ianb/pip``
* Subversion: ``http://varnish-cache.org/svn/trunk``
* Bazaar: ``lp:pasta``
