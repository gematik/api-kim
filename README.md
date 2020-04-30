# KIM-API Dokumentation

Author: gematik GmbH  
v0.1, 2020

![gematik logo](images/gematik_logo.jpg)

## Allgemeines

Die folgende Dokumentation beschreibt die systemspezifische Lösung von KOM-LE 1.5. Es werden insbesondere die Komponenten der Lösung sowie deren Schnittstellen dargestellt und erläutert. Die Version KOM-LE 1.5 ist vollständig abwärtskompatibel. Dadurch wird gewährleitstet das Teilnehmer einer früheren Version uneingeschränkt Nachrichten an Teilnehmern mit KOM-LE 1.5 versenden können.

Der Funktionsumfang für KOM-LE 1.5 erweitert sich um,

-   ✓ Aufhebung der Größenbeschränkung von Nachrichten

-   ✓ Optionale Integration des Clientmoduls in das PVS

-   ✓ Administrationsmodul für die Konfiguration

-   ✓ Unterstützung syntaktischer Nachrichtenkategorien

Die Einordung von KOM-LE 1.5 für das Release 4.0 liefert das entsprechende Systemdesign der TI. Weitere Details werden im Kapitel „Systemarchitektur“ im Systemdesign beschrieben.

## Systemarchitektur

Die folgende Abbildung gibt einen Überblick über die Systemarchitektur von KOM-LE 1.5

![kim overview](images/kim_overview.png)

[**Clientsystem**](docs/KIM_API.adoc)

-   **Clientmodul:**  
    Das Clientmodul kann jetzt optional in das Clientsystem integriert werden.

-   **Administrationsmodul:**  
    Die Erweiterung des Clientmoduls um das Administrationsmodul ermöglicht die Kommunikation mit dem Account Manager des Fachdienstes. Dadurch wird der Leistungserbringer in die Lage versetzt sich beim Fachdient zu registrieren, seinen Registrierungsstatus abzufragen oder eine Deregistrierung vorzunehmen. Zugleich kann über das Administrationsmodul das benötigte Clientzertifikat (PKCS\#12) heruntergeladen werden.

[**Fachdienst**](docs/Fachdienst.adoc)

-   **Account Manager:**  
    Für die einfache Verwaltung des Accounts eines KOM-LE-Teilnehmers, wird der Account Manager um ein Webservices erweitert.

-   **KOM-LE Attachment Service:**  
    Der Fachdienst wird um die Komponente KAS (KOM-LE Attachment Services) ergänzt, der die sichere Speicherung größerer Anhänge erlaubt.

[**Basisdienste**](docs/Basisdienste.adoc)

-   **Verzeichnisdienst:**  
    Um die Kompatibilität von KOM-LE 1.5 zu früheren Versionen zu gewährleisten, wird der Verzeichnisdienst mit einem neuen Attribut (*KIM-Version*) erweitert.

## Ordnerstruktur

Im Folgenden ist die Organisation der Ordnerstruktur dargestellt.

    KIM-API
    ├─ docs
    ├─ images
    ├─ samples
    ├─ src
    │   └── openapi
    │        ├── AccountManager.yaml
    │        └── AttachmentServices.yaml
    └── README.adoc

## Lizenz

Copyright 2020 gematik GmbH

## Links

[- Anwendungsfälle](docs/Anwendungsfaelle.adoc)  

**Produkttypen**  
[- Clientsystem](docs/KIM_API.adoc)  
[- Fachdienst](docs/Fachdienst.adoc)  

[- Basisdienste](docs/Basisdienste.adoc)  
[- Versionierung](docs/Versionierung.adoc)  
