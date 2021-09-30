# Welkom bij Project Notificatieservices

Project Notificatieservices wil het mogelijk maken dat Nederlandse overheidsorganisaties vaker en beter gebeurtenisgedreven ('event driven') werken. Daarvoor is op een aantal aspecten standaardisatie nodig. Project Notificatieservices richt zich primair op de ontwikkeling van een standaard berichtformaat voor geautomatiseerd uitwisselen van informatie over plaatsgevonden gebeurtenissen ('notificaties'). Er worden ook afspraken gemaakt over aspecten zoals de interactie tussen betrokken applicaties (bijv. voor geautomatiseerd abonneren op notificaties) en er worden aanbevelingen gedaan over zaken waar in de praktijk rekening mee moet worden gehouden.  

Het project een eerste stap is op weg naar effectief gebeurtenisgedreven werken binnen de overheid. Vergelijkbaar met hoe dit bij de Nederlandse API strategie verloopt zal dit meerdere jaren vergen en is samenwerking in de vorm van een community nodig. Als voorbereiding daarop wordt nu al samengewerkt met een community waarin zowel overheidsorganisaties als marktpartijen zijn vertegenwoordigd.

Doe mee en [ga aan de slag](./aan-de-slag.md) !

## Missie

*Bijdragen aan effectief gebeurtenisgedreven kunnen werken binnen de overheid.*

*Standaardiseren van het berichtformaat voor notificatieberichten.*

*Maken van afspraken over diverse aspecten van gebeurtenisgedreven werken.*

## Visie

*Een overheid die ook gebeurtenisgedreven werkt en daarmee snellere en betere dienstverlening kan leveren.*

## Strategie

We sluiten zoveel mogelijk aan bij wat wereldwijd gebruikelijk is (bijv. toepassing van het [publish-subscribe patroon](https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern)) en wat er aan standaarden vastgesteld of in ontwikkeling is. We gebruiken de [CloudEvents](https://cloudevents.io/) berichtspecificatie ('A specification for describing event data in a common way') als uitgangspunt voor het te ontwikkelen standaard berichtformaat voor notificaties. Aanvullend maken we afspraken over hoe we de CloudEvents berichtstandaard binnen onze overheidscontext toepassen. De resultaten hiervan zijn gebundeld op de pagina: [Berichtstandaard voor notificeren binnen de overheid](./notificatie-berichtformaat.md).

Voor het maken van afspraken over hoe we in de praktijk gebeurtenisgedreven werken gebruiken we ook andere specificaties. Bij ieder van de genoemde specificaties is beschreven wat we daarvan overnemen en hoe we er binnen onze context mee gaan werken. 

| Specificaties 	| Toepassing |
|---|---|
| CloudEvents specificatie voor berichten met gebeurtenisinformatie | [Berichtformaat voor notificaties](./notificatie-berichtformaat)|
| CloudEvents specificaties voor gebruik van de berichtstandaard met verschillende formaten (bijv. JSON) en protocollen (bijv. HTTP) | [Formaten en protocollen](./formaten-en-protocollen)|
| CloudEvents specificaties voor abonneren op notificaties en het kunnen filteren daarvan | [Abonneren en filteren](./abonneren-en-filteren)|
| CloudEvents specificatie voor het ('push')patroon waarbij notificaties op initiatief van een aanbieder worden verstrekt aan geabonneerde afnemers ||
| CloudEvents specificatie voor publiceren van informatie over beschikbare soorten gebeurtenissen | [Publiceren soorten gebeurtenissen](./publiceren-gebeurtenistypes) |
| AsyncAPI specificatie voor documenteren van API's bij gebruik van het Publish-Subcribe patroon | [AsyncAPI gebruik](./asyncapi-gebruik.md)|
| Open standaarden zoals benoemd door het Forum Standaardisatie| [Open standaarden](./open-standaarden.md)|

We gebruiken bovenstaande specificaties om een aantal aanbevelingen te doen. Op termijn kunnen ze onderdeel worden van de familiie van standaarden voor gebeurtenisgedreven werken binnen de Nederlandse overheid.   

## Status van de berichtstandaard

De berichtstandaard voor notificaties is in ontwikkeling. Momenteel heeft de standaard nog geen formele status. 
De planning is dat de standaard medio 2022 de status van Release Candidate krijgt. Dit houdt in dat er een 1.0 versie van de standaard is die in principe klaar is en geimplementeerd kan worden. Partijen die de berichtstandaard implementeren  kunnen gedurende de Release Candidate fase hun bevindingen terugkoppelen naar het project. Deze bevindingen kunnen leiden tot een nieuwe Release Candidate, of worden meegenomen in de definitieve 1.0 versie van de standaard. 
Op de [voortgangspagina](/docs/_content/achtergronddocumentatie/voortgang.md) wordt bijgehouden welke wijzigingen in de berichtstandaard zijn aangebracht.

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

Gebeurtenissen doen zich in vele vormen en binnen vele contexten voor. Bij uitvoering van het project is bewust gekozen voor een afbakening van de scope om te voorkomen dat er teveel vraagstukken tegelijkertijd moeten worden opgelost. Een belangrijke afbakening is bijv. dat het project zich richt op geautomatiseerde notificatie tussen applicaties binnen de overheid en niet op notificeren van mensen of bedrijven. Mogelijk zijn veel projectresultaten ook bruikbaar voor zaken die buiten scope zijn geplaatst maar dit zal in vervolgprojecten moeten blijken. [Toelichting op de projectscope](./projectscope) 

## Architectuur

Bij uitvoering van het project worden een aantal richtinggevende [architetuurprincipes](./architectuur/architectuurprincipes/README.md) gebruikt. 
In lijn daarmee zijn een aantal [architectuur-aanbevelingen](./architectuur/aanbevelingen/README.md) gedaan.
 
## Besluiten en aanbevelingen

Tijdens de uitvoering van het project zijn in overleg met de betrokken community en de werkgroep Berichtenstandaard verschillende soorten [besluiten](./besluiten) genomen. Vanuit teksten kan hiernaar worden verwezen als achtergrondinformatie en verantwoording van gemaakte keuzes. 
Op basis van opgedane kennis, uitgevoerde beproevingen en plaatsgevonden discussies worden ook een aantal [aanbevelingen](./aanbevelingen) gedaan over gebeurtenisgedreven werken in het algemeen en gebruik van de notificatie berichtstandaard in het bijzonder. 
