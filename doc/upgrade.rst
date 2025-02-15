===============
Upgrading guide
===============

To 1.x from 0.x
===============

From version 1.x, this bundle Reveal.js 4.x, and implement for it.
Due it, documentations for old version does not work to build correctly.

You have to lock version, or migrate source for next version.

revealjs_script_plugins
-----------------------

Reveal.js 4.x has big changes for usage of plugins from 3.x.

|THIS| is also adjust for this changes,
and need update ``revealjs_script_plugins`` .

.. code-block:: diff

    revealjs_script_plugins = [
        {
    +        "name": "RevealNotes",
    +        "src": "revealjs4/plugin/notes/notes.js",
    -        "src": "revealjs/plugin/notes/notes.js",
        },
        {
    +        "name": "RevealHighlight",
    +        "src": "revealjs4/plugin/highlight/highlight.js",
    -        "src": "revealjs/plugin/highlight/highlight.js",
    -        "options": """
    -            {async: true, callback: function() { hljs.initHighlightingOnLoad(); } }
    -        """
        },
    ]

* Changed structure from src and options to src and name.

  * | For 4.x, to use plugin for core,
    | add class name of it not source path,
    | and need to preload source by ``script`` tag.
  * | Class name is defined in plugin source.
    | You need find from source or ref documents (official plugin only)
  * In adding, does not accept options for plugins.

MORE: See `Using Plugins from Reveal.js document <https://revealjs.com/plugins/>`_

revealjs_css_files
------------------

If you use highlight plugin and specify bundled stylesheet file,
change path of stylesheet.
Style files is migrated to highlight plugin folder.

* Before: ``revealjs/lib/css/zenburn.css``
* After: ``revealjs4/plugin/highlight``
