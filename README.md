# Welkom bij Project Notificatieservices

Project Notificatieservices heeft als doel om de wijze van notificeren binnen de Nederlandse overheid te standaardiseren. Een belangrijk onderdeel daarvan is het komen tot een gestandaardiseerd berichtformaat voor het uitwisselen van notificatieberichten tussen applicaties.

Meer algemeen geldt dat het project een eerste stap is op weg naar meer en beter gebeurtenisgedreven ('event driven') werken binnen overheidsorganisaties. Dit zal, vergelijkbaar als bij de Nederlandse API strategie, meerdere jaren vergen en samenwerking in de vorm van een community vergen. Reden waarom we nu al werken met een community waaraan zowel overheidsorganisaties als marktpartijen deelnemen.

Doe mee en [get started](./getting-started.md) !

## Missie

*Standaardiseren van het berichtformaat voor notificatieberichten.*

*Maken van afspraken over en standaardiseren van aspecten van gebeurtenisgedreven werken.*

*Ontwikkelen van effectief gebeurtenisgedreven werken binnen de overheid.*


## Visie

*Een overheid die gebeurtenisgedreven werkt en daarmee haar dienstverlening verbetert.*


## Strategie

We standaardiseren door maximaal gebruik te maken van wat internationaal op dit vlak gebeurt. 

We gebruiken de [CloudEvents](https://cloudevents.io/) berichtspecificatie ('A specification for describing event data in a common way') als uitgangspunt voor het gestandaardiseerde berichtformaat voor notificaties. We maken aanvullend afspraken over hoe we de CloudEvents berichtstandaard binnen onze context toepassen in de [NLD-CloudEvents berichtstandaard](./NLD-CloudEvents-berichtstandaard.md). 

Omdat alleen specificatie van een berichtformaat onvoldoend is om in de praktijk effectief gebeurtenisgedreven te kunnen werken maken we gebruik van:
- de CloudEvents specificatie voor gebruik van de berichtstandaard met verschillende formaten (bijv. JSON) en protocollen (bijv. HTTP)
- de CloudEvents specificatie voor abonneren op en filteren van gebeurtenissen
- de CloudEvents specificatie voor het ('push')patroon waarbij notificaties op initiatief van een aanbieder worden verstrekt aan geabonneerde afnemers
- de CloudEvents specificatie voor publiceren en raadplegen van informatie over onderscheiden gebeurtenissen
- de AsyncAPI specificatie voor documenteren van API's bij gebruik van het Publish-Subcribe patroon.

We gebruiken bovenstaande specificaties om een aantal aanbevelingen te doen. Op termijn kunnen ze onderdeel worden van de familiie van standaarden voor gebeurtenisgedreven werken binnen de Nederlandse overheid.   

## Projectorganisatie

Opdrachtgever is het Ministerie van Binnenlandse Zaken. 
Opdrachtnemer is VNG Realisatie.
Bij de uitvoering zijn betrokken:
- bestuursorganen (bijv. gemeenten)
- uitvoeringsorganisaties (bijv. Logius)
- marktpartijen.


## Gebeurtenis, actoren en rollen

Op business-niveau onderscheiden we:
- **Gebeurtenis**: een plaatsgevonden voorval waarover informatie verstrekt wordt
- **(Dienst)aanbieder**: een organisatie die informatie over opgetreden gebeurtenissen verstrekt
- **(Notificatie)makelaar**: een  (eventueel aanwezige) organisatie die op basis van ontvangen informatie over gebeurtenissen notificaties aan geabonneerde afnemers verstrekt
- **(Dienst)afnemer**: een organisatie aan wie notificaties worden verstrekt.

Op applicatieniveau gebruiken we de CloudEvents terminologie en onderscheiden we:
- **Event**: een gegevensrecord dat gegevens over een gebeurtenis en de context daarvan bevat
- **Producer**: de applicatie die gebeurtenisinformatie verstrekt aan afnemers of een intermediair
- **Intermediair**: een, of meerdere, applicatie(s) die een rol spelen bij het overbrengen van gebeurtenisinformatie naar afnemers in de vorm van (meestal push)notificaties
- **Consumer**: een applicatie aan wie notificaties wordt verstrekt.

In de praktijk kunnen organisaties en applicaties een of meerdere rollen vervullen.

## Scope

Gebeurtenissen doen zich in vele vormen en binnen vele contexten voor. Hoewel de berichtenstandaard in vele situaties toepasbaar is bij uitvoering van het project de scope afgebakend als:




## Architectuur

Tijdens uitvoering van het project zijn een aantal leidende architetuurprincipes vastgesteld en zijn in lijn daarmee een aantal keuzes gemaakt waaronder keuzes om op een bepaalde manier gebruik te maken van de binnen de CloudEvents berichtenstandaard opgenomen berichtattributen. 

- **Architectuur Principes**: een verzameling vastgestelde [principes](./architectuur_principes/README.md).   [pr](.\architectuur_principes\README.md)   
- **Architecture Decision Log**: a collection of agreed-upon [beslissingen](./architectuur_beslissingen/README.md).

[beslissingen](./1.md)

Solution architecturen voor gebruik van de standaard vallen buiten de scope van het project. Deze moeten worden bepaald tijdens projecten waarbij notificeren een rol speelt zodanig dat de standaard optimaal passend binnen de context is toe te passen. 
 
## Aanbevelingen

Naast een berichtenstandaard worden aanbevelingen gedaan hoe de standaard effectief is te gebruiken en, meer algemeen, hoe gebeurtenisgedreven werken in de praktijk is vorm te geven: 

- [Applying natural language](./guidelines/language.md)
- [Adding references](./guidelines/references.md)
- [Developing](./guidelines/development.md)
- [Testing](./guidelines/testing.md)
- [Versioning](./guidelines/versioning.md)
