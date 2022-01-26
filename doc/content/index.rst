.. toctree::
    :maxdepth: 2
    :caption: Contents

Sacrifice to Sphinx
===================

Description
===========
Ticket backend for the ImportExport module.

System requirements
===================

Framework
---------
OTOBO 10.1.x

Packages
--------
ImportExport 10.1.2
 

Third-party software
--------------------
\-

Usage notes
===========
When using the extended synchronization, TicketID as well as Article_ArticleID have to be provided.

Configuration Reference
=======================

Core::ImportExport::ObjectBackend::ModuleRegistration
------------------------------------------------------------------------------------------------------------------------------

ImportExport::ObjectBackendRegistration###Ticket
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Object backend module registration for the import/export module.

Core::ImportExport::ObjectBackend::Ticket
------------------------------------------------------------------------------------------------------------------------------

ImportExport::Ticket::SynchronizeWithForeignDB
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
If activated additional data such as the history and links will be read from a foreign DB containing the exported tickets and added to the imported tickets on this system. This is only available for created, not for updated tickets.

Core::ImportExport::ObjectBackend::Ticket::ImportValueMaps
------------------------------------------------------------------------------------------------------------------------------

ImportExport::Ticket::ImportValueMap###001-Custom
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Value map. Define a key and a value map from import file to OTOBO.

About
=======

Contact
-------
| Rother OSS GmbH
| Email: hello@otobo.de
| Web: https://otobo.de

Version
-------
Author: |doc-vendor| / Version: |doc-version| / Date of release: |doc-datestamp|
