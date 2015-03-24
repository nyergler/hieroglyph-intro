.. rst-class::
   title_image

==========
Hieroglyph
==========

.. ifslides::

   .. figure:: /_static/hieroglyphs.jpg

      CC BY-SA http://www.flickr.com/photos/tamburix/2900909093/

   Beautiful slides from plaintext.

Hieroglyph
==========

- Builds slides from plaintext
- Utilize rich community of Sphinx extensions
- Write once, generate multiple formats

Why?
====

- Like me, you have a plaintext problem
- You're already writing documentation using Sphinx
- You want to keep your presentation content in sync with other
  documentation
- Why Not?

Installing & Using Hieroglyph
=============================

.. rst-class:: build

.. container::

   .. code-block:: bash

      $ pip install hieroglyph --user

   .. code-block:: bash

      $ hieroglyph-quickstart

   .. code-block:: bash

      $ make slides

Adding Hieroglyph
-----------------

Add **hieroglyph** as a Sphinx extension to your configuration::

  extensions = [
      'hieroglyph',
  ]

Build your slides::

  $ sphinx -b slides output/slides

Writing Your Document
=====================

- First and second level headings become slides
- Directives for splitting slides, creating additional slides
- Otherwise it's just ReStructured Text!

Styling Slides
==============

- Slides are just HTML
- The heading level is added as a class; ie, ``level-2``
- You can add a custom CSS file to most themes by adding a
  ``custom_css`` theme options::

    slide_theme_options = {'custom_css':'custom.css'}

- Custom CSS files are contained in your documentation's static files
  directory (usually ``_static``)

Write Once
==========

.. code-block:: rst

   PDB 101
   =======

   .. only:: not slides

      Let's start with the most common way people use PDB.

   Explicit Trace Points
   ---------------------

   .. literalinclude:: /samples/fibonacci_trace.py
      :line-classes: 13(arrow-line)
      :emphasize-lines: 14

   .. rst-class:: column-break-before

   .. code-block:: none
      :emphasize-lines: 3

      $ python fibonacci_trace.py 5
      > fibonacci_trace.py(12)<module>()
      -> print (fib(int(sys.argv[-1])))
      (Pdb)

Generate Many Formats
=====================

Documentation

.. figure:: /_static/pdb-html.png

.. nextslide::

Slides

.. figure:: /_static/pdb-slides.png

Thank you!
==========

* http://hieroglyph.io/
* http://github.com/nyergler/hieroglyph
* @nyergler
* nathan@yergler.net
