# Software Architecture Document Reddingsbrigade Deventer

# Inleiding
In dit document staan het architectureel ontwerp van het content management systeem van de website van Reddingsbrigade Deventer. 
Dit systeem wordt in verder in dit document Dengdir genoemd, wat een anagram van "redding" is.    

## Achtergrond
Een aantal jaar geleden is besloten om de website van Reddingsbrigade Deventer te vernieuwen. Het systeem van toen was sterk verouderd 
en kon zeer slecht op mobiele apparaten(telefoons, tablets) gebruikt worden. Er is toen gekozen om over te stappen naar een site in Wordpress. 
Deze heeft een tijdje gedraaid totdat er een update van de onderliggende taal werdt toegepast. Hierdoor gingen er een aantal onderdelen kapot. Het bleek dat het lastig 
was om Wordpress, en het zoiso al vrij moeilijk was om een feature toe te voegen aan Wordpress. 

## Opdracht
Het is de bedoeling om een CMS op te zetten welke makkelijk uit te breiden is met nieuwe features, makkelijk te onderhouden is voor 
de content beheerder en makkelijk te onderhouden is voor de ontwikkelaars. 

# Definities en Afkortingen

| Afkorting | Definitie |
| --- | --- |
| RBD | Reddingsbrigade Deventer |
| CMS | Content Management Systeem |

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
| S1 | Contentbeheerder | Contentbeheerders beheren de content van de website. Zij zullen vooral pagina's aanpassen | 
| S2 | Ontwikkelaar | Ontwikkelaars zullen zich vooral bezig houden met het onderhouden en uitbreiden van het CMS |
| S3 | Bezoeker | Bezoekers gebruiken het CMS om pagina's te bezoeken. |
| S4 |  |  |
| S5 |  |  |
| S6 |  |  |
| S7 |  |  |

## Concerns
In dit hoofdstuk staan de verschillende concerns van de stakeholders. Deze worden geprioriteerd van 0 tot 10 waarbij 0 lage 
prioriteit aanduidt en 10 hoge prioriteit

| Code | Stakeholder code | Concern | Prioriteit | 
| --- | --- | --- | --- |
| C1 | S1 | Ik wil de content van een pagina kunnen aanpassen. | 10 |
| C2 | S1 | Ik wil nieuwe pagina's kunnen maken. | 10 |
| C3 | S1 | Ik wil pagina's kunnen verwijderen | 10 |
| C4 | S1 | Ik wil pagina's kunnen verbergen | 6 |
| C5 | S1 | Ik wil restricties op pagina's kunnen zetten, zodat er enige afscherming is voor bepaalde pagina's | 6 |
| C6 | S1 | Ik wil kunnen herleiden door wie een pagina is aangepast | 3 |
| C7 | S1 | Ik wil kunnen zien wanneer een pagina voor het laatst is aangepast | 3 |
| C8 | S2 | Ik wil er makkelijk achter kunnen komen waar een fout voorkomt in het systeem | 6 |
| C9 | S2 | Ik wil dat het systeem makkelijk uitbreidbaar is | 9 |
| C10 | S2 | Ik wil dat het systeem analyses op zichzelf kan uitvoeren om aan te tonen dat het systeem goed werkt | 2 |
| C11 | S1 | Ik wil feedback van het systeem krijgen als er problemen zijn met de content of wanneer een pagina niet benaderd kan worden | 4 |
| C12 | S | Ik wil |  |
| C13 | S | Ik wil |  |
| C14 | S | Ik wil |  |
| C15 | S | Ik wil |  |
| C16 | S | Ik wil |  |
| C17 | S | Ik wil |  |
| C18 | S | Ik wil |  |
| C19 | S | Ik wil |  |
   

# Architectureel Significante Requirements
In dit hoofdstuk wordt er gekeken naar de verschillende requirements die voor de architectuur relevant zijn. Op basis van de ISO 25010 
standaard worden quality attributes aan de verschillende requirements gekoppeld. Hier wordt later in het document dieper op ingegaan en 
worden keuzes gemaakt om aan de requirements te kunnen voldoen.   

| ASR Code | QA | Omschrijving |
|---|---|---|
| ASR-1 |  |  |
| ASR-2 |  |  |
| ASR-3 |  |  |

## High-level Usecases

![High level Usecase diagram]

Het high level usecase diagram maakt duidelijk welke stakeholders welke acties kan uitvoeren.

### Usecase beschrijvingen

| # | Usecase 1 |
| --- | --- |
| Naam | Boekhouding Beheren |
| Actor | Penningmeester |
| Beschrijving | De penningmeester voert de acties voor het beheren van de boekhouding uit. Deze acties zijn bijvoorbeeld het maken van grootboeken, invoeren van betalingen, etc. |
| Pre-conditie | De penningmeester is ingelogd |
| Post-conditie | De penningmeester heeft zijn beheeracties uitgevoerd |

| # | Usecase 2 |
| --- | --- |
| Naam | Nieuws beheren |
| Actor | Commissie, Bestuur |
| Beschrijving | De commissie of bestuur voert de acties uit voor het beheren van het nieuws. Dit kan zijn het aanmaken van een nieuwsitem, een nieuwsitem aanpassen of een nieuwsitem verwijderen. |
| Pre-conditie | De commissie of bestuur is ingelogd |
| Post-conditie | De commissie of bestuur heeft zijn beheeracties uitgevoerd |

| # | Usecase 3 |
| --- | --- |
| Naam | Kalender beheren |
| Actor | Commissie, Bestuur |
| Beschrijving | De commissie of bestuur voert de acties uit voor het beheren van de kalender. Dit kan zijn het aanmaken van een kalenderitem, een kalenderitem aanpassen of een kalenderitem verwijderen. |
| Pre-conditie | De commissie of bestuur is ingelogd |
| Post-conditie | De commissie of bestuur heeft zijn beheeracties uitgevoerd |

| # | Usecase 4 |
| --- | --- |
| Naam | Website beheren |
| Actor | Commissie, Bestuur |
| Beschrijving | De commissie of bestuur voert de acties uit voor het beheren van de website. Dit kan zijn het maken, aanpassen of verwijderen van pagina's of instellingen wijzigen |
| Pre-conditie | De commissie of bestuur is ingelogd |
| Post-conditie | De commissie of bestuur heeft zijn beheeracties uitgevoerd |

| # | Usecase 5 |
| --- | --- |
| Naam | Bewakingen indelen |
| Actor | Commissie |
| Beschrijving | De commissie  |
| Pre-conditie | De commissie of bestuur is ingelogd |
| Post-conditie | De commissie of bestuur heeft zijn beheeracties uitgevoerd |


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