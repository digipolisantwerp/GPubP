# Release Notes GPubP - Content beheer 
Hier vind je de release notes van **GPubP - Content beheer**, één van de onderdelen van het [Generiek Publicatie Platform](https://acpaas.digipolis.be/nl/product/generiek-publicatie-platform). 

De release notes zijn chronologisch gesorteerd met de meeste recente release eerst. De badges geven aan over welk onderdeel het gaan en in welk stadia het zich bevindt. 
- [![Generic badge](https://img.shields.io/badge/Core|Contrib-gray.svg)]() Gaat de release over de core of over een contributie module.
-  [![Generic badge](https://img.shields.io/badge/Core|Contrib-DEV-yellow.svg)]() zijn alle features die momenteel ontwikkeld worden en nog niet beschikbaar zijn.
- [![Generic badge](https://img.shields.io/badge/Core|Contrib-ACC-blue.svg)]() zijn alle features die we momenteel aan't testen zijn. Deze zullen weldra gereleased worden.
- [![Generic badge](https://img.shields.io/badge/Core|Contrib-PRD-green.svg)]() zijn alle features die gereleased zijn voor gebruik.

*The formaat is gebaseerd op [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), en maakt gebruik van [Semantic Versioning](https://semver.org/spec/v2.0.0.html).* 

## [Unreleased] [![Generic badge](https://img.shields.io/badge/Core-DEV-yellow.svg)]()
-  **Content** 
	- Configuratie waarbij werken met afbeeldingen en linken in een Tekstvak met opmaak per profiel bepaald kan worden 
	- Tekstlijn component krijgt een extra configuratie optie waarmee je een masker kan invoeren
	- De adres component zal een extra optie krijgen waarbij je per content type kan bepalen of er met beelden en linken gewerkt kan worden.
	- Alle autocomplete velden zullen een 'clear' (x) optie krijgen zodat je een nieuwe zoek kan lanceren in de lijst
	- Voor componenten die bestaan uit waardelijsten (key/value) zoals keuzerondjes, keuzelijsten, etc, kan je de data ervan eenvoudig importeren
	- Een nieuw Formulier Referentie content component waarmee je een formulier kan kiezen dat gemaakt is via de [Form Composer](https://formcomposer.antwerpen.be). 
    - Audio component met ondersteuning voor SoundCloud
    - Location picker widget improvements 

## [4.1.5]: 2022-01-10 [![Generic badge](https://img.shields.io/badge/Core-PRD-green.svg)]()
Bekijk de [Jira release notes](https://jira.antwerpen.be/secure/ReleaseNote.jspa?projectId=14114&version=15735).
### Changed
-   **Algemeen:** Verbeterde copy doorheen de applicatie
-  **Content** 
	- Autocomplete bij het zoeken naar een content referentie (interne link) vlotter gemaakt. 
	- De filter op datum in het Content overzicht werkt nu op laatst bijgewerkt (ipv publicatiedatum)
	- Het verwijderen van een filter in het content overzicht werkt vlotter
	- Het invoeren van content zal iets 'rustiger' worden qua stijl (lettertype groottes worden beter afgestemd)

### Fixed
-  **API**
	- Views filteren via de API is uitgebreid, [zie hier voor de mogelijkheden](https://docs.google.com/spreadsheets/d/1pylW8fwLd0IxLAyQ7WaYRH6sbRow7xsv8lRZSUXf3-k/edit#gid=0).
	- Interne linken die gelegd worden in een Tekstvak met opmaak worden nu volwaardig door de API geleverd. 
-  **Content** 
	- Boodschap netjes gezet wanneer je een UUID kopiëert.
	- WCAG compliancy optie bij bestanden wordt nu correct gevalideerd
	- Hulpteksten van invoervelden beter uitgelijnd
	- Een content component verwijderen van een content type en daarna terug toevoegen (obv een ander content component) is verbeterd. 
    - Wanneer validatie foutboodschappen uit beeld voorkwamen zag je ze niet staan. Nu zal het systeem naar boven/onder scrollen bij het bewaren van een content en zo de fout in beeld brengen.  
    - Editeren van een component in een Paragraaf op een content type zal geen crash meer veroorzaken. (Wit scherm aka WSOD)
-  **Navigatie:** Een content item in de navigatieboom hangen is nu verbeterd voor kleinere schermen. 
-  **Rollen & Rechten** 
    -  De rollen op tenant zijn terug zichtbaar, zo kan de rol Content Beheerder opnieuw uitgedeeld worden.
    -  Gebruikers zonder een tenant rol (tenant of content beheerder), kunnen nu ook bestanden uploaden.
-  **Workflow:** Een content item met een status dat niet in de workflow voorkomt zal geen crash meer veroorzaken. (Wit scherm aka WSOD)
-  **Workflow** 
   - Je kan nu een workflow correct verwijderen op site niveau.
   - Als je een transitie maakt naar dezelfde status, bv van Werkversie naar Werkversie dan worden nu de rechten en de workflow configuratie correct nageleefd.

## 2021-12-23  [![Generic badge](https://img.shields.io/badge/Tabel%20Contrib-PRD-green.svg)]()
- De Tabel module is beschikbaar op Productie.

## [4.1.2]: 2021-12-14 [![Generic badge](https://img.shields.io/badge/Core-PRD-green.svg)]()
Bekijk de [Jira release notes](https://jira.antwerpen.be/secure/ReleaseNote.jspa?projectId=14114&version=15538).
### Added
-  **Algemeen:** Visuele feedback bij het kopiëren van een UUID
-  **Content** 
	- Nieuw content component '*Cross site content referentie*'. Laat toe om naar content items te refereren over sites heen binnen dezelfde tenant.
	- Content types kunnen nu verwijderd worden
	- Het URL patroon heeft nu een default waarde [item:slug]
	- Views verwijderen
-  **Navigatie:** Navigatie items kunnen nu vervangen worden
-  **Search:** Elasticsearch "reindex" functionaliteit voor alle content items (enkel voor antwerpen site binnen A-stad tenant)


### Changed
-  **Algemeen:** Verbetering van teksten (microcopy)
-  **API**
	- Swagger voor occurrences calls
	- Content events op kafka gebeuren nu met een kleine delay om rekening te houden met async cache invalidatie
-  **Content**
	- Statussen in filter overzicht
	- Het gedrag van de bewaar knop van een content item is bijgewerkt
	- UI voor verwijderen van content type/blok
	- Verbeterpunten voor URL patroon, oa. er is nu steeds een default patroon
	- Bevat operator binnen view voor CKEditor veld
-  **Systeem:** Server monitor calls
-  **Workflow**
	- Statussen in content overzicht en filter
	- Implementatie statussen call op site niveau

### Fixed
-  **Algemeen:** Verwijderen vanfilters op overview pagina's is verbeterd (was incosistent)
-  **API:** Sorteren van content items o.b.v een view is verbeterd
-  **Content**
	- Verwijderen van onbewaarde content items
	- De padding van een Tekstvak met opmaak (gelijkgetrokken met andere invoer velden)
	- Crop positie bij afbeeldingen
	- Positionering van de hulptekst bij een titel invoer veld
	- WCAG Compliancy behaviour binnen content component
	- Validatie alert wordt nu getoond wanneer er op opslaan geklikt wordt en er zijn validatie fouten bij de invoer van content
	- Interne link bij het zoeken naar content items is verbeterd
	- Velden met een standaard waarde kunnen niet meer gewist worden
	- Conflicterende (= gelijke) namen tussen oude en nieuwe content componenten veroorzaakt foutieve validatie, data van oude, verwijderde content component "X" van type Y wordt geprojecteerd op nieuw toegevoegde content component "X" van type Z
	- Opslaan van preview settings voor een site
-  **Navigatie:** Na het publiceren van een content item wordt de status van het navigatie item meteen aangepast
-  **Workflow**
	- Bewaren van content item in zijn huidige status, ongeacht de ingestelde workflow geeft nu correcte info weer
	- Ophalen van site rollen is verbeterd (gaf soms een 403)
	- Als gebruiker met de "workflow update" rechten kan je nu de instellingen van een workflow bewerken
