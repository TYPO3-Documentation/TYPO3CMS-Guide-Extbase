.. include:: ../../../Includes.txt

f:debug.render
==============

This ViewHelper contains a debuggable version of f:render. It performs the same rendering operation but wraps the output
with HTML that can be inspected with the admin panel in FE.

This ViewHelper replaces `f:render` when the admin panel decides (see ViewHelperResolver class). It is also possible to
use explicitly by using `f:debug.render` instead of the normal `f:render` statement.

Properties
----------

section
~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Section to render - combine with partial to render section in partial

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

partial
~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    Partial to render, with or without section

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

arguments
~~~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    Array of variables to be transferred. Use {_all} for all variables

:aspect:`Default value`
    []

:aspect:`Mandatory`
    No

optional
~~~~~~~~
:aspect:`Variable type`
    Boolean

:aspect:`Description`
    If TRUE, considers the *section* optional. Partial never is.

:aspect:`Default value`
    FALSE

:aspect:`Mandatory`
    No

default
~~~~~~~
:aspect:`Variable type`
    Mixed

:aspect:`Description`
    Value (usually string) to be displayed if the section or partial does not exist

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No

contentAs
~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    If used, renders the child content and adds it as a template variable with this name for use in the partial/section

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    No
