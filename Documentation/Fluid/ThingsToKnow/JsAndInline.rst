.. include:: ../../Includes.txt

JavaScript and Fluid Inline Syntax
==================================

When Fluid ViewHelpers are used in mixed templates containing complex JavaScript blocks, you might come across a 
situation in which a ViewHelper using inline syntax doesn't get interpreted.

This is usually caused by the Fluid parser detecting one or more of the JavaScript expressions as so-called accessors,
which normally would indicate a variable should be rendered. When this happens, the internals of Fluid may not properly
detect ViewHelper calls that follow the block that was parsed as accessor but was JavaScript.

In this case you can manipulate the JavaScript block to prevent it from being detected as accessor. There are several
ways you can achieve this: by using a normal ViewHelper, or wrap the JavaScript part in a CDATA block, or disrupt the
detection of beginnign and closing curly braces.

Problem
-------

::

 <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.1//EN" "http://www.w3.org/TR/xhtml11/DTD/xhtml11.dtd">
 <html xmlns="http://www.w3.org/1999/xhtml">
 <head>
     <script src="http://code.jquery.com/jquery-1.10.1.min.js"></script>
     <script src="http://layout.jquery-dev.net/lib/js/jquery.layout-latest.js"></script>
     <script type="text/javascript">
         var myLayout;

         $(document).ready(function() {
             myLayout = $('body').layout({
                 north__size:                27
                 ,    north__initClosed:            false
                 ,    north__initHidden:            false
                 ,    center__maskContents:        true // IMPORTANT - enable iframe masking
             });
         });
     </script>

     <link rel="stylesheet" type="text/css" href="{f:uri.resource(path:'Css/main.css')}" />
 </head>
 <body>

 <div class="ui-layout-north">
     Some dumb text
 </div>
 <div class="ui-layout-center">
     Lorem ipsum
 </div>

 </body>
 </html>

The ViewHelper in the following line::

 <link rel="stylesheet" type="text/css" href="{f:uri.resource(path:'Css/main.css')}" />

…is not interpreted but ignored by Fluid.

Solutions
---------

- Prevent Fluid from detecting the JavaScript as if it were Fluid, by adding disrupting markup. For example:::

  myFunction = function () {
    <f:comment>This comment is here to prevent Fluid's parser from detecting the content of brackets</f:comment>
    // some simple JS that would otherwise be detected by Fluid
    foo()
  };

- Disrupt detection of opening and closing curly braces::

  myFunction = function () <f:format.raw>{</f:format.raw>
    // some simple JS that would otherwise be detected by Fluid
    // IMPORTANT! f:comment cannot be used here, it has to be a VH that allows the tag body to output!
    foo()
  };

- Wrap the JavaScript part in CDATA::

   <![CDATA[
   ...
   ]]>

- Wrap the JavaScript block using the :ref:`f:format.cdata <f-format-cdata>` ViewHelper::

   <f:format.cdata>
     <script type="text/javascript">
       var myLayout;
       $(document).ready(function() {
         myLayout = $('body').layout({
           north__size: 27,
           north__initClosed: false,
           north__initHidden: false,
           center__maskContents: true // IMPORTANT - enable iframe masking
         });
       });
     </script>
   </f:format.cdata>
