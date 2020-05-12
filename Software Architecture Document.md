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
| S5 | Webmaster | De webmaster beheert de webite van de reddingsbrigade |
| S6 | Lid | De leden kunnen via de website  |

## Concerns


# Architectureel Significante Requirements

| ASR Code | QA | Omschrijving |
|---|---|---|
|  |  | Applicatie moet testbaar zijn |
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

## Decision Forces View

## Decision Relationship View

## Decision detail View

# References 


[Systeem overview]: http://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/Jelmergu/ReddingsbrigadeDeventerDocs/master/Diagrams/SoftwareArchitectureDocument/Systeem_overview.puml