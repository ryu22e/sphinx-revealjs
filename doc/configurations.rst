==============
Configurations
==============

|THIS| can build multiple presentations.
You can configure in ``conf.py`` for all presentations.

Basic configurations
====================

.. confval:: revealjs_static_path

   :Type: ``list``
   :Default: ``[]`` (empty)
   :Example: ``["_static"]``

   List of static files directory ( same as :confval:`sphinx:html_static_path` )

.. confval:: revealjs_js_files

   :Type: ``list``
   :Default: ``[]`` (empty)
   :Example: ``["custom.js"]``

   List of using custom css (same as :confval:`sphinx:html_js_files` ).

   When you want to use JS that does not related revealjs, can use this.

.. confval:: revealjs_css_files

   :Type: ``list``
   :Default: ``[]`` (empty)
   :Example: ``["custom.css"]``

   List of using custom css (same as :confval:`sphinx:html_css_files` ).

   If you want to customize presentation by CSS, write external css and use it.

Style Configurations
====================

.. confval:: revealjs_style_theme

   :Type: ``str``
   :Default: ``black``
   :Example: ``moon``, ``custom.css``

   Theme name of stylesheet for Reveal.js.

   * | If value does not have suffix ``.css``,
     | use bundled Reveal.js theme(included ``revealjs/css/theme``).

Presentation Configurations
===========================

.. confval:: revealjs_use_section_ids

   :Type: ``boolean``
   :Default: ``False``

   If this is set ``True``,
   inject ``id`` attribute into ``section`` element (parent of headerings).
   This means that change format of internal links (default is numbering style).

.. confval:: revealjs_script_files

   :Type: ``List[str]``
   :Default: ``[]``
   :Example: ``["presentation.js"]``

   List of sources that render as ``script`` tags.

   There is bundled Reveal.js script at ``revealjs/js/reveal.js``.

   Example:

   .. code-block:: html

      <div>
        <!-- Presentation body -->
      </div>
      <!-- here!! -->
      <script src="_static/revealjs/js/revealjs.js"></script>
      <script src="_static/presentation.js"></script>

.. confval:: revealjs_script_conf

   :Type: ``str or dict``
   :Default: ``None``

   Configuration of Reveal.js presentation.
   This value is used as options of ``Reveal.initialize`` in output files.

   * If value is string type, handle as raw javascript code.
   * If value is dict object, convert to json string at internal.

   Example 1: case of str

   .. code-block:: py

      revealjs_script_conf = """
      {
          controls: false,
          transition: 'zoom',
      }
      """

   .. code-block:: html

      <div>
        <!-- Presentation body -->
      </div>
      <script src="_static/revealjs/js/revealjs.js"></script>
      <!-- here!! -->
      <script>
        let revealjsConfig = {};
        revealjsConfig = Object.assign(revealjsConfig, {
          controls: false,
          transition: 'zoom',
        });
        revealjs.initialize(revealjsConfig);
      </script>

   Example 2: case of dict

   .. code-block:: py

      revealjs_script_conf = {
          "controls": False,
          "transition": "zoom",
      }

   .. code-block:: html

      <div>
        <!-- Presentation body -->
      </div>
      <script src="_static/revealjs/js/revealjs.js"></script>
      <!-- here!! -->
      <script>
        let revealjsConfig = {};
        revealjsConfig = Object.assign(revealjsConfig, JSON.parse('{"controls": false, "transition": "zoom"}'));
        revealjs.initialize(revealjsConfig);
      </script>

   example 1 and 2 are behaving same.

.. confval:: revealjs_script_plugins

   :Type: ``List[Dict]``
   :Default: ``[]``

   List of plugin configurations.
   If this value is set, render ``script`` tag after source script tags.

   There are bundled Reveal.js plugins at ``revealjs/plugin``.

   Example:

   .. code-block:: py

      revealjs_script_plugins = [
          {
              "src": "revealjs4/plugin/highlight/highlight.js",
              "name": "RevealHighlight",
          },
      ]

   .. code-block:: html

      <div>
        <!-- Presentation body -->
      </div>
      <script src="_static/revealjs/js/revealjs.js"></script>
      <script src="_static/revealjs/plugin/highlight/highlight.js"></script>
      <!-- here!! -->
      <script>
        let revealjsConfig = {};
        revealjsConfig.plugins = [RevealHighlight,];
        revealjs.initialize(revealjsConfig);
      </script>

Font configurations
===================

.. note::

   These configurations will be dropped when version 2.x.

   You can use raw CSS or `googlefonts-markup <https://pypi.org/project/googlefonts-markup/>`_ instead of these.

.. confval:: revealjs_google_fonts

   :Type: ``dict``
   :Default: ``[]``
   :Example: ``[]``

   List of using fonts from `Google Fonts <https://fonts.google.com/>`_.
   If this value is set, render ``link`` and ``style`` tags into html.

.. confval:: revealjs_generic_font

   :Type: ``str``
   :Default: ``sans-serif``
   :Example: ``serif``, ``monospace``

   If you use ``revealjs_google_fonts``, set last of ``font-family`` style.
