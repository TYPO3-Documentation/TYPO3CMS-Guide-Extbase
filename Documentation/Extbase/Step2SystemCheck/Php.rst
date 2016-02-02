.. ÄÖÜäöüß 

PHP
===

Although TYPO3 4.5 ran fine using PHP 5.2, we recommend that you use the newest possible 
stable version of PHP - at least 5.3.2. Newer versions of TYPO3 - since 6.0 - make use of 
PHP namespacing, which requires PHP 5.3.8 (or newer, wherever possible).

TYPO3 4.5 could run in an environment with a PHP memory_limit of 64MB. Newer versions of 
TYPO3 benefit from more memory, so your system should allow a setting of at least 128MB.

If you're using xdebug, you might run into difficulty because of the number of nested 
Partials. This produces the following error message::

  Maximum function nesting level of '100' reached, aborting!

If this happens, edit your php.ini file and increase the nesting level limit: we suggest 
500 as a minimum value. If this is insufficient, then set it higher still, to 1000::

  xdebug.max_nesting_level = 500