=========
Changelog
=========

ver 1.5.2
=========

:date: 2022-04-29
:base: Reveal.js 4.3.1

Fixes
-----

* Work ``revealjs-break`` directive in ``dirrevealjs`` builder (#109)
* Inherit behavior of any nodes from ``html`` builder to ``dirrevealjs`` builder (#108)

Deprecated
----------

Mark as deprecated(logging.warning) to drop at version 2.x (updated from v1.5.0)

* Snake-cased directive ( ``revealjs_slide``, ``revealjs_section`` and ``revealjs_break`` )
* CSS Font configurations ( ``revealjs_google_fonts`` and ``revealjs_generic_font`` )
* Passing values from ``html_js_files`` to ``revealjs_js_files``

ver 1.5.1
=========

:date: 2022-04-21
:base: Reveal.js 4.3.1

Fixes
-----

* Add ``role="main"`` into ``page.html`` for searching by Sphinx (#102)

Misc
----

* Add documentation link into metadata (PyPI)

ver 1.5.0
=========

:date: 2022-04-11
:base: Reveal.js 4.3.1

Features
--------

* Add ``dirrevealjs`` builder to generate all pages as ``index.html``

Deprecated
----------

Mark as deprecated(logging.info) to drop at version 2.x

* Snake-cased directive ( ``revealjs_slide``, ``revealjs_section`` and ``revealjs_break`` )
* CSS Font configurations ( ``revealjs_google_fonts`` and ``revealjs_generic_font`` )
* Passing values from ``html_js_files`` to ``revealjs_js_files``
* Full-support for Python 3.6.x

ver 1.4.6
=========

:date: 2022-03-26
:base: Reveal.js 4.3.1 (updated)

(Only update reveal.js)

ver 1.4.5
=========

:date: 2022-03-06
:base: Reveal.js 4.3.0 (updated)

(Only update reveal.js)

ver 1.4.4
=========

:date: 2021-12-12
:base: Reveal.js 4.2.1 (updated)

(Only update reveal.js)

ver 1.4.3
=========

:Date: 2021-11-20
:Reveal.js: v4.2.0

(None updates for features)

Extra
-----

* Update classifiers of PyPI

  * Fix key of license
  * Add other keys

ver 1.4.2
=========

:Date: 2021-11-20
:Reveal.js: v4.2.0

(None updates for features)

Extra
-----

* Update test matrix of GitHub Actions to confirm that this supports python 3.10
* Update classifiers of PyPI because test cases passed under Python 3.10 and Sphinx 4.x

ver 1.4.1
=========

:Date: 2021-11-16
:Reveal.js: v4.2.0 **(updated)**

Fixes
-----

* Replace reveal.js to use right bundle version.

ver 1.4.0
=========

:Date: 2021-11-13
:Reveal.js: v4.2.0 **(updated)**

New features
------------

* Add ``revealjs_js_files`` for ``conf.py`` to set JS file. (#77)
* ``revealjs_script_conf`` accepts dict types (#56)

Extra
-----

* Change test codes from nose to py.test

ver 1.3.1
=========

:date: 2021-07-17
:base: Reveal.js 4.1.3

Fixes
-----

* ``revealjs-fragments`` for paragraph contents (#71)

ver 1.3.0
=========

:date: 2021-07-11
:base: Reveal.js 4.1.3

New features
------------

* Support some attributes of sections
* Add directive ``revealjs-code-block`` to line highlighting for reveal.js
* Add kebab-case directives for currently snake-case directives

  * `revealjs-slide` <= `revealjs_slie`
  * `revealjs-section` <= `revealjs_section`
  * `revealjs-break` <= `revealjs_break`
  * `revealjs-fragments` <= `revealjs_fragments`

ver 1.2.1
=========

:date: 2021-06-13
:base: Reveal.js 4.1.3 (updated)

(Only update reveal.js)

ver 1.2.0
=========

:date: 2021-06-06
:base: Reveal.js 4.1.1 (updated)

New fetures
-----------

* When builder writes contents from extensions, use same of html builder

ver 1.1.0
=========

:date: 2021-04-04
:base: Reveal.js 4.1.0

New features
------------

* Add option to add ``id`` attribute per sections (#59, #61)

  * Supporting label syntax of Sphinx.

Extra
-----

* Fix dependencies for development environment
* Add ``package.json`` to notify updates reveal.js by dependabot

ver 1.0.1
=========

:date: 2021-01-30
:base: Reveal.js 4.1.0

Fixes
-----

- Change order of link tags for css files (#40, #41)
- Rename test case function names for duplicated (#42, #54)

ver 1.0.0
=========

:date: 2021-01-03
:base: Reveal.js 4.1.0

Breaking changes
----------------

In this version, ``sphinx-revealjs`` bundle Reveal.js version 4.x,
and does not supporting to work with Reveal.js 3.x.

If you want to migrate presentation source for this version,
please see `migration example <./docs/migrations>`_. 

New features
------------

* Using Revealjs 4.x (use 4.1.0)

  * With supporting multiple presentation management in single documentation

Drop
----

* Bundle and implements for Revealjs 3.x

ver 0.12.1
==========

:date: 2020-12-12

Fixes
-----

* Restrict effect of ``revealjs_section`` for only one section ( `PR#36 <https://github.com/attakei/sphinx-revealjs/pull/36>`_ )

ver 0.12.0
==========

:date: 2020-06-21

New features
------------

* Config variables:

  * ``revealjs_js_files``
  * ``revealjs_css_files``
  * ``revealjs_static_path``

Updates
-------

* ``revealjs_google_fonts`` use Google Fonts API version 2
* Change css selector for google-fonts

Drop
----

* Remove ``zenburn.css`` from default included css files
* Ignore ``html_js_files``, ``html_css_files`` and ``html_static_path``

ver 0.11.0
==========

:date: 2020-04-17

Features
--------

* | Add new config variables ``revealjs_style_theme``,
  | ``revealjs_google_fonts``,``revealjs_generic_font``,
  | ``revealjs_script_files``, ``revealjs_script_conf``
  | and ``revealjs_script_plugins``
* | **Breaking:** Change directive option,
  | from ``config`` to ``conf`` in ``RevealjsSlide`` directive.

Drop
----

* | **Breaking:** Remove config variables
  | ``revealjs_theme`` and ``revealjs_theme_options``.

Fixes
-----

* Use black for formatting

ver 0.10.1
==========

:date: 2020-04-09

Fixes
-----

* Change bundle Reveal.js (3.9.1 -> 3.9.2)

ver 0.10.0
==========

:data: 2020-03-25

Features
--------

* Change bundle Reveal.js (3.8.0 -> 3.9.1)
* Add support version (3.8, author's default)

Fixes
-----

* In development, depend by ``sphinxcontrib-gtagjs``. (use in demo)

Extra
-----

* Change license (MIT -> Apache-2.0)
* Use poetry as build environment

ver 0.9.0
=========

:date: 2019-12-22

Fixes
-----

* google-fonts default options is changed for not to render in template.
* Adjusting templates based by sphinx basic theme. (short breaking)

  * Enable ``metatags`` , ``scripts`` and more template values.

ver 0.8.0
=========

:date: 2019-11-11

Features
--------

* Add new config option ``google_font`` to set google-font style.

ver 0.7.0
=========

:date: 2019-10-28

Features
--------

* Add new directive ``revealjs_fragments`` to use Fragment.

ver 0.6.1
=========

:date: 2019-09-12

Fixes
-----

* Remove tag that refer source not exits

ver 0.6.0
=========

:date: 2019-07-31

Features
--------

* Add new directive ``revealjs_break`` to split sections.

  * Updated demo

Extra
-----

* Add docstrings any sources. (ignore tests)
* Remove Pipenv.
* Migrate metadata and options from ``setup.py`` into ``setup.cfg`` .
* Use bumpversion for versioning

ver 0.5.1
=========

:date: 2019-06-30

Extra
-----

* Update Reveal.js from 3.7.0 to 3.8.0


ver 0.5.0
=========

:date: 2018-12-31

Features
--------

* Revealjs initialize config accept from sphinx document config
* Revealjs initialize config accept from ``revealjs_slide`` directive


ver 0.4.1
=========

:date: 2018-12-21

Fixes
-----

* ``revealjs_section`` directive of source apply for itself only

ver 0.4.0
=========

:date: 2018-12-10

Features
--------

* It can select theme per presentations.


ver 0.3.1
=========

First public release on PyPI.
