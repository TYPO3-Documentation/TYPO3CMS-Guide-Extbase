.. include:: ../Includes.txt

Domain Driven Design
====================

The source code of a piece of software can quickly become very messy without 
a clear structure. We've come across individual extensions which contain three 
separate PDF generators. Did the developer forget that he'd already added a 
PDF generator? Or did the extension need to use features of a PDF generator which 
weren't possible with the former solution? Who knows?

Many programmers recognize early on that it's critical for source code to be clearly 
structured. Whether during the implementation of a PDF generator, making a connection 
to a database, writing a log file, or sending an email. This principle is called 
*Domain Driven Design*. The biggest advantage is the separation of functionality, 
so that the developer can focus on a specific problem. When working on a PDF 
generator, there's no need to delve into the code for database connectivity. 

Extbase itself works according to this principle, so you don't need to give much 
thought to how you should structure the necessary files: the structure is already 
defined and common to all extensions.

Thanks to validation features within the domain model, you can instruct the model to 
“cross-check” itself. In the event that data is invalidated at some point in the 
handling process, error handling kicks in and warns the developer, so that the 
invalid data doesn't get written to the database.

Domain Driven Design should form a part of the concept phase; where appropriate, 
even during discussions with your client. This means that the data structure can be 
planned from the beginning of the process, ensuring that problems can be avoided 
during the development phase. This ensures a more efficient programming phase and less 
work for both the programmer and the client.

By using ubiquitous language, you ensure that everyone working on the project uses 
the same terminology - avoiding misunderstanding by always referring to data properties 
and system features in the same way. As in most development environments, it's 
recommended that you use English terms for extension development. This avoids issues with 
special characters, such as those with umlauts, in (for example) database column names.