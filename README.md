# KIM - Dokumentation

<img src="images/gematik_logo.svg" alt="gematik_logo" width="50%"/>
image:https://shields.io/badge/AttachmentService v2.30-blue[link="https://github.com/gematik/api-kim/blob/KIM-Hotfix-1.5.2/src/openapi/AccountManager.yaml"]

## Allgemeines
<a href="https://fachportal.gematik.de/fachportal-import/files/gemSpec_VZD_V1.14.0.pdf" rel="some text">![Foo](https://img.shields.io/badge/Ichderjens-v1.5-blue)</a>

Die folgende Dokumentation beschreibt die systemspezifische Lösung von KIM 1.5 und baut auf dem Konzept von KIM 1.0 "Kommunikation Leistungserbringer" gemäß **[gemSysL_KOMLE]** auf. An dieser Stelle werden insbesondere die Komponenten der Lösung sowie deren Schnittstellen dargestellt und erläutert. Die Version KIM 1.5 ist vollständig abwärtskompatibel. Dadurch wird gewährleistet, dass Teilnehmer mit einer früheren Version uneingeschränkt Nachrichten an Teilnehmer versenden können, die bereits KIM 1.5 verwenden.

Der Funktionsumfang der KIM Version 1.5 erweitert sich gegenüber KIM 1.0 wie folgt:

-   die Aufhebung der Größenbeschränkung von Nachrichten

-   die optionale Integration des Clientmoduls in das Primärsystem

-   ein Administrationsmodul für die Konfiguration des Nutzer-Accounts

-   das Einrichten von Abwesendheitsnotizen

-   die Unterstützung syntaktischer Nachrichtenkategorien

-   die Unterstützung von Multikonnektor-Umgebungen

_Hinweis: Seit März 2020 verwendet die gematik die Bezeichnung „KIM – Kommunikation im Medizinwesen“ für die Anwendung KOM-LE. Diese neue Benennung findet sich insbesondere in Informationsmaterialien für die Zielgruppe Leistungserbringer, sowie in Presseveröffentlichungen. Eine Umbenennung in den technisch-normativen Dokumenten wie Spezifikationen, Konzepten, Zulassungsdokumenten etc. mit Ausnahme von Angaben zu Domänen, E-Mail-Adressen, technischen Schnittstellen, Parametern u.ä. ist aktuell nicht geplant._

## Systemarchitektur

Die folgende Abbildung gibt einen Überblick über die Systemarchitektur von KIM 1.5. Die Änderungen bei Komponenten und Schnittstellen von KIM 1.0 zu KIM 1.5 sind in der Abbildung rot dargestellt. 

<!---
![kim overview](images/kim_overview.png)
-->
<p align="center">
<img src="images/kim_overview.png" alt="drawing" style="width:85%"/>
</p>

[**Clientsystem**](docs/KIM_API.adoc)

-   **Clientmodul:**  
    Das Clientmodul kann jetzt optional in das Clientsystem (z. B. Primärsystem) integriert werden.

-   **Administrationsmodul:**  
    Die Erweiterung des Clientmoduls um das Administrationsmodul ermöglicht die Kommunikation mit dem Account Manager des Fachdienstes zur Administration und Konfiguration des Accounts eines KIM-Teilnehmers.

[**Fachdienst**](docs/Fachdienst.adoc)

-   **Mail Server:**  
    Der Mail Server stellt die Schnittstell `I_Message_Service` bereit und wird über die Protokolle SMTP und POP3 angesprochen. In der KIM Version 1.5 wurden am Mail Server keine Änderungen vorgenommen. 

-   **Account Manager:**  
    Für die einfache Verwaltung des Accounts sowie das Einrichten von Abwesenheitsnotizen eines KIM-Teilnehmers bietet der Account Manager ab der KIM Version 1.5 zwei Webservices (`I_AccountManager_Service` und `I_AccountLimit_Service`) an. 

-   **KOM-LE Attachment Service:**  
    Der Fachdienst wird um die Komponente KOM-LE Attachment Services (KAS) erweitert, der die sichere Speicherung größerer Client-Mails (E-Mail-Daten) ermöglicht. Die Komponente kann über die REST-Schnitstelle `I_Attachment_Service` erreicht werden.

[**Verzeichnisdienst**](docs/Verzeichnisdienst.adoc)

<!--- -   **Verzeichnisdienst:**  
--->

-    Um die Kompatibilität von KIM 1.5 zu früheren Versionen zu gewährleisten, wird der Verzeichnisdienst um eine neue Datenstruktur `komLeData` ergänzt. 
-   Der Verzeichnisdienst wird um die REST-Schnittstelle `I_Directory_Application_Maintenance` erweitert. 

## Ordnerstruktur

Im Folgenden ist die Organisation der Ordnerstruktur dargestellt.

    KIM-API
    ├─ docs
    ├─ images
    ├─ samples
    │   ├──── KAS
    │   │    └── MultipleAttachments.zip
    │   └──── SMIME-Profil.zip
    ├─ src
    │   ├──── openapi
    │   │    ├── AccountLimit.yaml
    │   │    ├── AccountManager.yaml 
    │   │    └── AttachmentServices.yaml
    │   ├──── plantuml
    │   │    └── Fachdienst	
    │   └──── schema
    │        └── Attachment_schema.json
    ├── LICENSE	
    ├── README.md
    └── ReleaseNotes.md

## Ausbaustufen
Mit der Einführung von KIM unterstützt die gematik das Gesundheitswesen durch einen sektorenübergreifenden, sicheren E-Maildienst. In mehreren Versionen wird der Funktionsumfang von KIM kontinuierlich erweitert. Aktuell existieren die folgenden Versionen mit ihren dazugehörigen aktuellen Releases.

| &nbsp;  | KIM 1.0   | KIM 1.5| 
|---------| --------        | --------|
 | Release | [R3.1.3-11](https://fachportal.gematik.de/fileadmin/Fachportal/Downloadcenter/Releases/Konzepte_und_Spezifikationen/OPB3.1_R3.1.3_Hotfix11_Spezifikationen_20220209.zip)        | [KIM 1.5.2](https://fachportal.gematik.de/downloadcenter/releases/release-402-und-produkttyp-und-anwendungsreleases-1#c5189)|

Weitere Informationen zu den Versionen finden Sie hier: [KIM](https://fachportal.gematik.de/anwendungen/kommunikation-im-medizinwesen)

## Referenzierte Dokumente
Die nachfolgende Tabelle enthält die in der vorliegenden Online Dokumentation referenzierten Dokumente der gematik zur Telematikinfrastruktur. Deren zu diesem Dokument jeweils gültige Versionsnummer entnehmen Sie bitte der aktuellen, auf der Internetseite der gematik veröffentlichten Dokumentenlandkarte, in der die vorliegende Version aufgeführt wird.

| [Quelle]             | Herausgeber: Titel|
|----------------------| --------| 
 | **[gemSysL_KOMLE]**  | gematik: Systemspezifisches Konzept Kommunikation Leistungserbringer (KOM-LE)| 
 | **[gemSMIME_KOMLE]** | gematik: S/MIME-Profil Kommunikation Leistungserbringer (KOM-LE)  |
 | **[gemSpec_CM]**     | gematik: Spezifikation KOM-LE-Clientmodul|
 | **[gemSpec_FD]**     | gematik: Spezifikation Fachdienst KOM-LE|
 | **[gemSpec_VZD]**    | gematik: Spezifikation Verzeichnisdienst|
 | **[gemSpec_OM]**     | gematik: Übergreifende Spezifikation Operations und Maintenance|

## Weiterführende Seiten

[- Anwendungsfälle](docs/Anwendungsfaelle.adoc)  

**Produkttypen**  
[- Clientsystem](docs/KIM_API.adoc)  
[- Fachdienst](docs/Fachdienst.adoc) <br>
[- Verzeichnisdienst](docs/Verzeichnisdienst.adoc)    

**Leitfaden für Primärsystemhersteller**  
[- Primärsystem](docs/Primaersystem.adoc)  

**Diverses**  
[- Authentisierung](docs/Authentisierung.adoc)  
[- Versionierung](docs/Versionierung.adoc)  

**Referenz-Implementierungen**  
[- KIM-Attachment-Service](https://github.com/gematik/kim-attachment-service) <br>
[- KIM-Thunderbird Plugin](https://github.com/gematik/app-thunderbird-kim-plugin)

## Lizenzbedingungen
Copyright (c) 2022 gematik GmbH

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License. 
