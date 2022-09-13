# KIM API

Notes: Since April 2021 KIM is no longer a part of a gematik document release. Starting with KIM v1.5.1 it will be develop in a separate branch (see also https://fachportal.gematik.de/anwendungen/kommunikation-im-medizinwesen). 

## KIM v1.5.2-Hotfix - Release Notes
New feature
- added new operation to revoke deregistration to I_AccountManager_Service in v2.3.0
- added new integrity checks to ensure correct setting of the from header in an e-mail
- added an example for processing of an email that needs to be stored at the kas

Changes
- I_AccountManager_Service added some additional response codes
- updated I_Attachment_Service to v2.3.0 based on some changes on response codes
- updated I_AccountLimit_Servic to 1.1.0 based on setting a minimum value for maxMailSize
- removed I_Directory_Application_Maintenance from this repo and replaced references to the github repository of the vzd
- replaced sequence diagrams with plantuml based ones

## KIM v1.5.2 - Release Notes 

New feature 
- added new interface I_AccountLimit_Service (see [I_AccountLimit_Service](https://github.com/gematik/api-kim/blob/master/src/openapi/AccountLimit.yaml) for more details)
- added description of the interface: I_AccountLimit_Service in document "KIM_API.adoc"
- added new chapter AV-Service in implementation guideline for PS in document "Primaersystem.adoc"
- added X-KIM-Sendersystem Header Element in implementation guideline for PS in document "Primaersystem.adoc"

Changes 
- updated I_AccountManager_Service to v2.2.0 (see [I_AccountManager_Service](https://github.com/gematik/api-kim/blob/master/src/openapi/AccountManager.yaml) for more details)
- updated I_Attachment_Service to v2.2.0 (see [I_Attachment_Service](https://github.com/gematik/api-kim/blob/master/src/openapi/AttachmentService.yaml) for more details)
- updated I_Directory_Application_Maintenance to 1.1.2 (see [I_Directory_Application_Maintenance](https://github.com/gematik/api-kim/blob/master/src/openapi/DirectoryApplicationMaintenance.yaml) for more details)
- refactored the API in document "KIM_API.adoc"
- refactored the descriptions of the interfaces in document "Fachdienst.adoc"
- updated the description of VZD in document "Verzeichnisdienst.adoc"
- updated the overview of KIM use cases in document "Anwendungsfaelle.adoc"
- updated examples of interface releases in URL in document "Versionierung.adoc"
- added description of the interface I_AccountLimit_Service in document "Authentisierung.adoc"
- updated SMTP/POP3-Benutzername in implementation guideline for PS in document "Primaersystem.adoc"
- refactored startpage in document "Readme.md"

## KIM v1.5.1 - Release Notes 

New feature 
- added support for Multi-Konnektor environments 
- updated operations for registration process 
- added new operations for user administration 
- added new operations for out of office messages
- added new operations to port an TelematikID to new mail address 
- added new interface DiretoryApplicationMaintenance v1.0.0 
- added JSON-Web-Token for authentication 
- added HTTP-Auth for uploading files to KAS 

Changes 
- updated I_AccountManager_Service to v2.0.0 (see [I_AccountManager_Service](https://github.com/gematik/api-kim/blob/master/src/openapi/AccountManager.yaml) for more details) 
- updated I_Attachment_Service to v2.0.0 (see [I_Attachment_Service](https://github.com/gematik/api-kim/blob/master/src/openapi/AttachmentService.yaml) for more details) 
- refactored the API of KAS and Account Manager in KIM_API.adoc 
- refactored the overview of KIM use cases in Anwendungsfaelle.adoc 
- refactored implementation guideline for PS in Primaersystem.adoc
- renamed parameter in Attachment_schema.json 
- updated the description of VZD in Basisdienste.adoc 
- added new section Authentisierung.adoc 
- updated folder structure in Readme.md

# KIM v1.5

The specification KIM (KOM-LE) v1.5 is a part of gematik document release 4 
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

## Document Release 4.0.0

- removed limiting of message sizes
- enabled the integration of the client module in the PVS (optional)
- embedded administration module for the configuration of the KIM account
- support for syntactic message categories
