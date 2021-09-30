# Welkom bij Project Notificatieservices

Project Notificatieservices wil het mogelijk maken dat Nederlandse overheidsorganisaties vaker en beter gebeurtenisgedreven ('event driven') werken. Daarvoor is onder andere standaardisatie op een aantal nodig op een aantal aspecten. Project Notificatieservices richt zich primair op de ontwikkeling van een gestandaardiseerd berichtformaat voor geautomatiseerd uitwisselen van informatie over plaatsgevonden gebeurtenissen ('notificaties'). Er worden ook afspraken gemaakt aspecten zoals de interactie tussen betrokken applicaties (bijv. voor geautomatiseerd abonneren op notificaties) en er worden aanbevelingen gedaan over zaken waar in de praktijk rekening mee moet worden gehouden.  

Het project een eerste stap is op weg naar meer en beter gebeurtenisgedreven werken binnen de overheid. Vergelijkbaar met hoe dit bij de Nederlandse API strategie verloopt zal dit meerdere jaren vergen en is samenwerking in de vorm van een community nodig. Als voorbereiding daarop wordt nu al samengewerkt met een community waarin zowel overheidsorganisaties als marktpartijen zijn vertegenwoordigd.

Doe mee en [ga aan de slag](./aan-de-slag.md) !

## Missie

*Bijdragen aan effectief gebeurtenisgedreven kunnen werken binnen de overheid.*

*Standaardiseren van het berichtformaat voor notificatieberichten.*

*Maken van afspraken over diverse aspecten van gebeurtenisgedreven werken.*

## Visie

*Een overheid die waar nodig gebeurtenisgedreven werkt en daarmee haar dienstverlening verbetert.*

## Strategie

We sluiten zoveel mogelijk aan bij wat internationaal al op dit vlak is afgesproken en in ontwikkeling is. 

We gebruiken de [CloudEvents](https://cloudevents.io/) berichtspecificatie ('A specification for describing event data in a common way') als uitgangspunt voor het gestandaardiseerde berichtformaat voor notificaties. We maken aanvullend afspraken over hoe we de CloudEvents berichtstandaard binnen onze overheidscontext toepassen. De resultaten hiervan zijn gebundeld op de pagina: [Berichtstandaard voor notificeren binnen de overheid](./berichtstandaard.md). 

Voor het maken van afspraken over hoe we in de praktijk gebeurtenisgedreven werken maken we gebruik van bestaande specificaties en beschrijven we hoe we die binnen onze context toepassen. In gevallen waarbij afsrpaken worden gemaakt over hoe de interactie tussen actoren verloopt gebruiken we ook wel over een 'patroon'. 

| Specificaties 	| Toepassing |
|---|---|
| CloudEvents specificatie voor berichten met gebeurtenisinformatie | [Berichtformaat voor notificaties](./notificatie-berichtformaat)|
| CloudEvents specificaties voor gebruik van de berichtstandaard met verschillende formaten (bijv. JSON) en protocollen (bijv. HTTP) | [Formaten en protocollen](./formaten-en-protocollen)|
| CloudEvents specificaties voor abonneren op notificaties en het kunnen filteren daarvan | [Abonneren en filteren](./abonneren-en-filteren)|
| CloudEvents specificatie voor het ('push')patroon waarbij notificaties op initiatief van een aanbieder worden verstrekt aan geabonneerde afnemers ||
| CloudEvents specificatie voor publiceren van informatie over beschikbare soorten gebeurtenissen | [Publiceren soorten gebeurtenissen](./publiceren-gebeurtenistypes) |
| AsyncAPI specificatie voor documenteren van API's bij gebruik van het Publish-Subcribe patroon | [async-api-gebruik](./asyncapi-gebruik)|
| Open standaarden zoals benoemd door het Forum Standaardisatie| [Open standaarden](./open-standaarden)|

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

Gebeurtenissen doen zich in vele vormen en binnen vele contexten voor. Bij het ontwikkelen van de berichtenstandaard is de volgende scopeafbakening gehanteerd:

| Binnen scope 	| Buiten scope |
| --- | --- |
| Van overheid naar overheid (G2G) | Notificeren van mensen (G2C), bedrijven (G2B, B2B) |
| Notificeren door en van applicaties (M2M) | Notificeren bij microservices , serverless functies, Internet of Things  |
| 1 op N notificeren | 1 op 1 notificeren |
| 1-weg communicatie - Fire and forget | 2-weg communicatie Procesorkestratie, choreografie |
| Gedistribueerd: binnen en over organisaties heen | |
| Gebeurtenissen met en zonder gegevenswijzigingen in bronregistraties | |
| Open en closed data  / Open en closed diensten | |
| Beschrijven nut en noodzaak van gebeurtenisgedreven werken | Doel van en verwerking door afnemers |
| Randvoorwaarden benoemen (juridisch, technisch, organisatorisch, beveiliging, …) | Randvoorwaarden invullen |
| Informatie, o.a. beschrijving van diverse stijlen, patronen en protocollen| | 
| Aanbevelingen, afspraken, (concept) standaarden | Technische architectuur, realisatie van voorzieningen  |
| Notificatie gerelateerde functionaliteit voor vervolgopvraging bij informatiearm notificeren| Algemene functionaliteit voor vervolgopvraging bij  |informatiearm notificeren |

Opmerking: de ontwikkelde berichtstandaard is mogelijk ook bruikbaar voor toepassingen die buiten de projectscope vallen.

## Architectuur

Bij uitvoering van het project worden een aantal richtinggevende [architetuurprincipes](./architectuur/architectuurprincipes/README.md) gebruikt. 
In lijn daarmee zijn een aantal [architectuur-aanbevelingen](./architectuur/aanbevelingen/README.md) gedaan.
 
## Aanbevelingen

Naast een berichtenstandaard worden aanbevelingen gedaan hoe de standaard effectief is te gebruiken en, meer algemeen, hoe gebeurtenisgedreven werken in de praktijk is vorm te geven: 
