# Release 1.5.1
## KIM v1.5.1 - Release Notes New feature - added support for Multi-Konnektor environments - updated operations for registration process - added new operations for user administration - added new operations for out of office messages - added new operations to port an TelematikID to new mail address - added new interface DiretoryApplicationMaintenance v1.0.0 - added JSON-Web-Token for authentication - added HTTP-Auth for uploading files to KAS Changes - updated I_AccountManager_Service to v2.0.0 (see [I_AccountManager_Service](https://github.com/gematik/api-kim/blob/master/src/openapi/AccountManager.yaml) for more details) - updated I_Attachment_Service to v2.0.0 (see [I_Attachment_Service](https://github.com/gematik/api-kim/blob/master/src/openapi/AttachmentService.yaml) for more details) - refactored the API of KAS and Account Manager in KIM_API.adoc - refactored the overview of KIM use cases in Anwendungsfaelle.adoc - refactored implementation guideline for PS in Primaersystem.adoc - renamed parameter in Attachment_schema.json - updated the description of VZD in Basisdienste.adoc - added new section Authentisierung.adoc - updated folder structure in Readme.md

# KIM v1.5

The specification KIM (KOM-LE) 1.5 is a part of gematik document release 4 
(see also https://fachportal.gematik.de)

## Document Release 4.0.1 - Hotfix 1

New feature
- added a KAS sample for multiple attachments

Changes
- updated I_AccountManager_Service to v1.2.0 (see [I_AccountManager_Service](https://github.com/gematik/api-kim/blob/master/src/openapi/AccountManager.yaml) for more details)
- updated I_Attachment_Service to v1.0.0 (see [I_Attachment_Service](https://github.com/gematik/api-kim/blob/master/src/openapi/AttachmentService.yaml) for more details)
- updated API for primary systems: restriction added for creating message IDs during message creation
- refactored the API of KAS and Account Manager in KIM_API.adoc
- replaced SMIME-Profil.zip with a new version to represent changes of header field Message-ID for both inner and outer email
- updated folder structure in Readme.md

-------------------------------------------------------------------------------

## Document Release 4.0.1

New features

- included implementation guideline for PS
- added subchapter versioning added
- added JSON schema for attachments
- added KIM S/SMIME sample messages

Changes

- added errorcode 413 in operation add_Attachment in I_Attachment_Service
- added parameter referenceID in I_AccountManager_Service
- updated folder structure in Readme.md

-------------------------------------------------------------------------------

## Document Release 4.0.0

- removed limiting of message sizes
- enabled the integration of the client module in the PVS (optional)
- embedded administration module for the configuration of the KIM account
- support for syntactic message categories