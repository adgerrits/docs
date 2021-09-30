# Terminologie


## Gebeurtenis, actoren en rollen (todo)

Het 

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
