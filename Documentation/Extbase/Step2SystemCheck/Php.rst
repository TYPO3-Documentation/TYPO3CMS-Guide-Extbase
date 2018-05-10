.. include:: ../../Includes.txt 

PHP
===

If you're using xdebug, you might run into difficulty because of the number of nested 
Partials. This produces the following error message::

  Maximum function nesting level of '100' reached, aborting!

If this happens, edit your php.ini file and increase the nesting level limit: we suggest 
500 as a minimum value. If this is insufficient, then set it higher still, to 1000::

  xdebug.max_nesting_level = 500
