
git-hub
=======

A command to load up the git-hub project page associated with your project.

Setup
-----

* Copy the ``git-hub`` file into your path.
* Set the ``GIT_BROWSER`` environment variable to the name of a command which
  will open the URL provided in the first argumentin your preferred browser. For
  Firefox on Linux, simply ``firefox`` will suffice.

Usage
-----

Run ``git hub`` in your project repository.

Configuration
-------------

The script expects ``GIT_BROWSER`` to be set. See **Setup** above.

You can specify the github project name and author using the ``hub.author`` and
``hub.project`` git config values.

If they are not set, it uses the ``origin`` remote as explained below.


What Does It Do?
----------------

The command first checks to see if you have the config values ``hub.author`` and
``hub.project``. If they are set, it builds the target URL from those simply by
doing::

   http://github.com/author/project

If they aren't both set, it falls back to get the value of ``remote.origin.url``
and parses the information out of that with ``sed``.

Which ever way it builds the URL, it relies on the ``GIT_BROWSER`` environment
variable to be set to provide a script for loading the URL in your preferred
browser.

Requirements
------------

* bash
* sed
* git

Name
----

I realise it is a bit presumptous to claim the git-hub name for such a minor
script. I would be happy to change it if it is already in use.


