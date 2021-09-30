# Architectuur Principe

## Naam

Eenduidig

## Stelling

De inhoud van berichtattributen worden zo goed mogelijk gespecificeerd.

## Beschrijving

Alle attribuutwaarden binnen notificatieberichten wordt zo goed mogelijk gespecificeerd zodat voor alle betrokken organisaties en applicaties duidelijk is wat de betekenis er van is. 

## Rationale

Bij notificeren zijn meerdere organisaties en applicaties betrokken. Door de waarden van in berichten opgenomen attributen goed te specificeren kunnen    interpretatieverschillen worden voorkomen. 

## Implicaties

Bij rubrieken waar dit mogelijk is moeten waardenlijsten worden gedefinieerd waarbij voor iedere waarde is beschreven wat de betekenis is.
Afnemers moeten weten wat de betekenis van attribuutwaarden is en daar bij verwerking van notificaties rekening mee houden. 
Met name bij attributen die domeinspecifieke contextinformatie is het van belang dat afnemers weten wat de betekenis daarvan is.
De betekenis van attributen in de bericht-payload valt buiten de scope van project Notificatieservices. 

## Voorbeelden

De waarde van berichtattribuut 'type' beschrijft wat voor soort gebeurtenis heeft plaatsgevonden. Afnemers moeten weten over welke soorten gebeurtenissen een aanbieder notificaties verstrekt en wat de precieze betekenis daarvan is. 
De waarde van berichtattribuut 'source' beschrijft uit welke bron notificatiegegevens afkomstig zijn. Afnemers moeten weten wat de betekenis van een bepaalde bronaanduiding is.