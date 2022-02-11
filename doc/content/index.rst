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
OTOBO 10.0.x

Packages
--------
ImportExport 10.0.1
 
Third-party software
--------------------
\-

Usage
=====
In the ImportExport section of the admin interface a new backend (Ticket) is available. General usage is the same as other ImportExport modules. Identifiers can be used for tickets and articles to potentially skip the article. Rules are as follows:
* TicketID or TicketNumber are required to be marked as identifier for ticket identification
* Article_ArticleID is required to be marked as identifier for article identification
* When using identification and the object is found in the system, tickets are just updated instead of created, articles are skipped
* Regardless of whether identification is used or not, if objects are created, TicketID and ArticleID will be generated newly by OTOBO, TicketNumber (if included) will be set to the one of the csv. The latter will lead to an import error if the TicketNumber already exists (no identification used), and can also be problematic if imported from a system with a different SystemID or TicketNumber generator - use with care.

Configuration Reference
=======================

Core::ImportExport::ObjectBackend::ModuleRegistration
------------------------------------------------------------------------------------------------------------------------------

ImportExport::ObjectBackendRegistration###Ticket
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Object backend module registration for the import/export module.

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
