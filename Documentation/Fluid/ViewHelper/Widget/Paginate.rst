.. include:: ../../../Includes.txt

f:widget.paginate
=================

A view helper for rendering a pagination of objects or arrays

Properties
----------

objects
~~~~~~
:aspect:`Variable type`
    Object

:aspect:`Description`
    Objects or arrays used for pagination

:aspect:`Default value`
    NULL

:aspect:`Mandatory`
    Yes

as
~~~~~~~~~
:aspect:`Variable type`
    String

:aspect:`Description`
    The name of the variable which contains the paginated objects

:aspect:`Default value`
    Empty String

:aspect:`Mandatory`
    Yes

configuration
~~~~~~~~~~
:aspect:`Variable type`
    Array

:aspect:`Description`
    Configuration of the pagination: itemsPerPage, insertAbove, insertBelow, maximumNumberOfLinks, addQueryStringMethod, section

:aspect:`Default value`
     itemsPerPage': 10, insertAbove: false, insertBelow: true, maximumNumberOfLinks: 99

:aspect:`Mandatory`
    No

Examples
--------

Pagination of a blog with required arguments
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

::

 <f:widget.paginate objects="{blogs}" as="paginatedBlogs">
   <f:for each="{paginatedBlogs}" as="blog">
     <h2>{blog.title}</h2>
     <p>{blog.text}</p>
   </f:for>
 </f:widget.paginate>

Pagination of a blog with custom configuration
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

:: 

 <f:widget.paginate objects="{blogs}" as="paginatedBlogs" configuration="{itemsPerPage: 5, insertAbove: 1, insertBelow: 0, maximumNumberOfLinks: 10}">
   <f:for each="{paginatedBlogs}" as="blog">
     <h2>{blog.title}</h2>
     <p>{blog.text}</p>
   </f:for>
 </f:widget.paginate>
