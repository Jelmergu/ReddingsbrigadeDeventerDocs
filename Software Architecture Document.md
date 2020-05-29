# Software Architecture Document Reddingsbrigade Deventer

# Inleiding
In dit document staan het architectureel ontwerp van de website van Reddingsbrigade Deventer. Voor Reddingsbrigade Deventer wordt een volledig vernieuwde website opgezet.   

## Achtergrond


## Opdracht

# Definities en Afkortingen

| Afkorting | Definitie |
| --- | --- |
| RBD | Reddingsbrigade Deventer |
| TCZR | Technische Commissie Zwemmend Redden |
| CBH | Commissie Bewaking en Hulpverlening |
| COW | Commissie Opleiding Waterhulpverlening |
| Lid | Een lid van RBD |

# Systeem Overview

![Systeem overview]

## Systeem onderdelen
| Systeemonderdeel | Omschrijving |
| --- | --- | 
| Browser | Dit is de browser van de client. Hierin wordt de website weergegeven. |
| Server | De server host de website en bijbehorende database |
| Website | De website bestaat uit een core en meerdere modules. |
| Core | De core van de website bevat de onderdelen welke door alle modules gebruikt kunnen worden. Modules registreren bij de core op welke manier zij aangeroepen kunnen worden. De core zorgt voor het opzetten en opvragen van de verbinding met de database. |
| Modules | De verschillende modules van het systeem. Een module kan een breed scala aan functies uitvoeren op de website. Modules zijn afhankelijk van de core, en kunnen zelf ook afhankelijk zijn van enkele andere modules. |

# Stakeholders en Concerns
In dit hoofdstuk staan de partijen welke belang hebben bij het eindresultaat.
## Stakeholders

| Code | Stakeholder | Omschrijving |
|---|---|---|
| S1 | Bestuur RBD | Het bestuur van RBD. |
| S2 | Penningmeester RBD | De penningmeester van RBD gebruikt de website voor het uitvoeren van zijn taak. |
| S3 | Secretaris | |
| S3 | Commissie Externe Communicatie  | Het beheer van de website valt onder de commissie externe communicatie. Deze commissie is geïntresseerd in het makkelijk kunnen aanpassen van de website |
| S4 | CBH | De CBH gebruikt de website als hulpmiddel om bewakingen te plannen en de juiste personen erbij indelen | 
| S5 | Webmaster | De webmaster beheert de webite van de reddingsbrigade aan de backend. |
| S6 | Lid | De leden kunnen via de website algemene informatie over de brigade vinden, zoals nieuws en de kalender. Tevens kunnen zij hier hun alle gegevens vinden die bij de reddingsbrigade bekend is |
| S7 | Externen | Externen kunnen via de website informatie krijgen over de brigade. Deze groep wordt opgesplitst bij het hoofstuk substakeholders. |

### Substakeholders
| Code | Stakeholder | Omschrijving |
|---|---|---|
| S7-A | Potentieel leden | Potentieel leden komen naar de website om informatie te krijgen over de brigade en over mogelijkheden om de sfeer te proeven. |
| S7-B | Organisatoren | Organisatoren organiseren een evenement en willen de reddingsbrigade hier bij hebben om toezicht te bewaken. Dit kan zijn omdat dit nodig is voor een vergunning of om RBD informatie/voorlichting te laten geven |
| S7-C |  | 

## Concerns
In dit hoofdstuk staan de verschillende concerns van de stakeholders. Deze worden geprioriteerd van 0 tot 10 waarbij 0 lage 
prioriteit aanduidt en 10 hoge prioriteit

| Code | Stakeholder code | Concern | Prioriteit | 
| --- | --- | --- | --- |
| C1 | S |  |  |
| C2 | S5 | Ik wil kunnen zien wanneer er een fout optreed in de website, zodat ik hier snel op kan reageren | 5 |
| C3 | S3 | Ik wil de content van de website kunnen aanpassen, zodat ik ervoor kan zorgen dat de website up to date blijft | 8 |
| C4 | S5 | Ik wil dat de content van de website aangepast kan worden door anderen, zodat ik niet verantwoordelijk ben voor de content van de website | 8 |
| C5 | S7-A | Ik wil informatie kunnen krijgen over RBD, zodat ik weet wat een reddingsbrigade inhoud | 8 |
| C6 | S7-A | Ik wil een idee kunnen krijgen over de sfeer bij RBD, zodat ik weet of het bij mij past | 7 |
| C7 | S7-B | Ik wil informatie kunnen krijgen over de beschikbaarheid van RBD, zodat ik weet of de RBD bij mijn evenement kan bewaken | 6 |
| C8 | S7-B | Ik wil informatie kunnen krijgen over hoe ik RBD kan benaderen | 7 |
| C9 | S4 | Ik wil een overzicht hebben van alle evenementen waar voor bewaakt moet worden, zodat ik boten en mensen kan indelen voor deze bewakingen | 4 |
| C10 | S4 | Ik wil een overzicht hebben van alle mensen met hun kwalificaties en beschikbaarheid voor het bewaken bij evenementen, zodat ik de bewakers kan indelen bij evenementen | 4 |
| C11 | S4 | Ik wil de bewakers kunnen inlichten over bewakingen waar zij op staan ingedeeld, zodat deze vlekkeloos kunnen verlopen | 4 |
| C12 | S3 | Ik wil nieuws kunnen delen, zodat externen een idee krijgen over wat RBD doet | 5 |
| C13 | S6 | Ik wil nieuws over de brigade kunnen zien, zodat ik op de hoogte kan blijven over wat er binnen de brigade zoal wordt gedaan | 5 |
| C14 | S2 | Ik wil de ledenadministratie kunnen bijhouden en bijwerken, zodat het ledenbestand up to date blijf | 8 |
| C15 | S2 | Ik wil de mogelijkheid hebben om de boekhouding te doen op de website | 7 |
| C16 | S1 | Ik wil toegang hebben tot de boekhouding om de penningmeester te kunnen controleren | 8 |
| C17 | S1 | Ik wil dat leden toegang hebben tot alle gegevens welke over zichzelf bekend zijn bij RBD, zodat de website aan de privacywetgeving voldoet | 10 |
| C18 | S6 | Ik wil inzicht kunnen krijgen in de gegevens welke bij RBD bekend zijn over mij, zodat ik mijn eigen privacy kan beschermen | 10 |
| C19 | S6 | Ik wil inzicht kunnen krijgen in de activiteiten van RBD welke er aan staan te komen, zodat ik op de hoogte ben van activiteiten waaraan ik misschien mee wil doen | 5 |
   

# Architectureel Significante Requirements

| ASR Code | QA | Omschrijving |
|---|---|---|
| ASR-1 | Testability | Applicatie moet testbaar zijn |
| ASR-2 | Co-existence | De applicatie moet kunnen werken op de bestaande server van RBD |
| ASR-3 | Interoperability | De applicatie moet data kunnen uitwisselen met het huidige systeem voor zolang de functionaliteiten van het huidige systeem nog niet zijn opgenomen in het nieuwe systeem |

## High-level Use Cases

## Qualtity Atrributes Requirements

## External Interfaces

## Technical Constraints

# Architectural Views
 
## Logical View

## Implementation View

## Process View

## Deployment View

## Architecturele Beslissingen
In dit hoofdstuk staan de verschillende architecturele beslissingen die zijn gemaakt om de website tot stand te kunnen brengen.

## Decision Relationship View
![Decision Relationship View]

## Decision detail View
| Naam | Programmeertaal |
| --- | --- |
| Versie | 1 |
| Status | Decided |
| Probleem/Issue | Voor het schrijven van een website zijn een aantal talen beschikbaar. Omdat het hier om een website gaat met veel functionaliteiten valt automatisch HTML af. |
| Decision | PHP |
| Alternatives | NodeJS<br>Java |
| Argumenten | Op de huidige server draait al PHP 7.4 en het huidige systeem maakt ook gebruik van PHP 7.4. Hierdoor wordt het makkelijker om het oude systeem uit te faseren |
| Gerelateerde beslissingen | - |
| Gerelateerde vereisten | ASR-2<br>ASR-3 |
| Geschiedenis | \[2020-05-20] PHP besloten |



| Naam | Template |
| --- | --- |
| Versie | 1 |
| Status | Decided |
| Probleem/Issue | |
| Decision |  |
| Alternatives |  |
| Argumenten |  |
| Gerelateerde beslissingen | - |
| Gerelateerde vereisten |  |
| Geschiedenis | \[2020-]  |
 

## Decision Forces View
### Programmeertaal
| Code | Description | Prioriteit | PHP | NodeJS | Java |
| --- | --- | --- | --- | --- | --- | 
| ASR-2 | De applicatie moet kunnen werken op de bestaande server van RBD | Hoog | ++ | + | \ | 
| ASR-3 | De applicatie moet data kunnen uitwisselen met het huidige systeem voor zolang de functionaliteiten van het huidige systeem nog niet zijn opgenomen in het nieuwe systeem | Hoog | ++ | + | + |
#### Legenda
| Code | -- | - | 0 | + | ++ | \ |  
| --- | --- | --- | --- | --- | --- | --- | 
| ASR-2 | De taal kan niet werken op de server | De taal zou met heel veel moeite kunnen werken op de server | De taal kan werken op de server, maar een programma moet nog geinstalleerd worden | Een of twee instellingen moeten aangepast worden om de taal te laten werken op de server | De taal draait al op de server | Onbekend en niet naar gekeken |
| ASR-3 | n.v.t | De taal kan niet uitwisselen met het huidige systeem | De taal kan wel uitwisselen met het huidige systeem, maar kost veel moeite | De taal kan uitwisselen met het systeem | De taal wordt ook voor het huidige systeem gebruikt | n.v.t |  


# References 


[Systeem overview]: http://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/Jelmergu/ReddingsbrigadeDeventerDocs/master/Diagrams/SoftwareArchitectureDocument/Systeem_overview.puml
[High level Usecase diagram]: http://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/Jelmergu/ReddingsbrigadeDeventerDocs/master/Diagrams/SoftwareArchitectureDocument/High_level_usecase_diagram
[Decision Relationship View]: http://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/Jelmergu/ReddingsbrigadeDeventerDocs/master/Diagrams/SoftwareArchitectureDocument/Decision_relationship_view.puml