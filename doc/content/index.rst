.. image:: ../images/otobo-logo.png
   :align: center
|

.. toctree::
    :maxdepth: 2
    :caption: Contents

Sacrifice to Sphinx
===================

Description
===========
Ticket backend for the ImportExport module. This backend allows to import and export tickets with their articles. It also supports the synchronization of the tickets with a foreign database, which can be used to import the history of the tickets.

System requirements
===================

Framework
---------
OTOBO 11.0.x

Packages
--------

Third-party software
--------------------
\-

Usage
=====
In the ImportExport section of the admin interface a new backend (Ticket) is available. General usage is the same as other ImportExport backends. Identifiers can be used for tickets and articles to potentially skip the article. Rules are as follows:

* TicketID or TicketNumber are required to be marked as identifier for ticket identification
* Article_ArticleID is required to be marked as identifier for article identification
* When using identification and the object is found in the system, tickets are just updated instead of created, articles are skipped
* Regardless of whether identification is used or not, if objects are created, TicketID and ArticleID will be generated newly by OTOBO, TicketNumber (if included) will be set to the one of the csv. The latter will lead to an import error if the TicketNumber already exists (no identification used), and can also be problematic if imported from a system with a different SystemID or TicketNumber generator - use with care.

The console commands Admin::ImportExport::Export and Admin::ImportExport::Import provide functionality on the command line.
Using the command line also allow chunked export and import.

In order to achieve better performance, some SysConfig setting are temporarily altered during Export and Import. This means that
ElasticSearch has to be reindexed after an import.

There is an import feature called extended synchronisation. This feature can be activated via the SysConfig.
When using the extended synchronization, TicketID as well as Article_ArticleID have to be provided. This means that the history of the tickets will be imported. Additionally, the links of the tickets will be imported.

If old, imported ticket numbers with a different system ID (important, but with the same ticket number generator) are also to be recognized in follow-ups, install the *LegacySystemIDSupport* package and enter the original system ID in the settings.

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
| Email: hello@otobo.io
| Web: https://otobo.io

Version
-------
Author: |doc-vendor| / Version: |doc-version| / Date of release: |doc-datestamp|
