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
| S7 | Externen |  |

## Concerns
In dit hoofstuk staan de verschillende concerns van de stakeholders. Deze worden geprioriteerd van 0 tot 10 waarbij 0 lage 
prioriteit aanduid en 10 hoge prioriteit

| Code | Stakeholder code | Concern | Prioriteit | 
| --- | --- | --- | --- |
| C1 | S6 | Ik wil de gegevens over mij kunnen bekijken welke bij RBD bekend zijn | 10 |
| C2 | S5 | Ik wil kunnen zien wanneer er een fout optreed in de website, zodat ik hier snel op kan reageren | 5 |
| C3 | S3 | Ik wil de content van de website kunnen aanpassen, zodat ik ervoor kan zorgen dat de website up to date blijft | 8 |
| C4 | S5 | Ik wil dat de content van de website aangepast kan worden door anderen, zodat ik niet verantwoordelijk ben voor de content van de website | 8 |  


# Architectureel Significante Requirements

| ASR Code | QA | Omschrijving |
|---|---|---|
| ASR-1 | Testability  | Applicatie moet testbaar zijn |
|  |  |  |

## High-level Use Cases

## Qualtity Atrributes Requirements

## External Interfaces

## Technical Constraints

# Architectural Views
 
## Logical View

## Implementation View

## Process View

## Deployment View

## Decision Relationship View
![Decision Relationship View]

## Decision Forces View

### Programmeertaal
| | |


## Decision detail View
| Naam | Programmeertaal |
| --- | --- |
| Versie | 1 |
| Status | Decided |
| Probleem/Issue | In welke taal gaat de applicatie geschreven worden |
| Decision | PHP 7.4 |
| Alternatives | none |
| Argumenten | | 
| Gerelateerde beslissingen | |
| Gerelateerde vereisten | |
| Geschiedenis | 2020-05-20 PHP 7.4 besloten | 

# References 


[Systeem overview]: http://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/Jelmergu/ReddingsbrigadeDeventerDocs/master/Diagrams/SoftwareArchitectureDocument/Systeem_overview.puml
[Decision Relationship View]: http://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/Jelmergu/ReddingsbrigadeDeventerDocs/master/Diagrams/SoftwareArchitectureDocument/Decision_relationship_view.puml