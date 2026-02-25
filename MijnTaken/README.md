# Inleiding

Op deze pagina is de Taken-service beschreven. De taken-service bestaat uit een beschrijving van afspraken, standaarden en referentiecomponenten aangevuld met interactiepatronen, ontwerpbesluiten en aanbevelingen.

Tijdens het behandelen van een zaak, kan het voorkomen dat nog extra informatie (bijvoorbeeld documenten of situatietekeningen) van de indiener nodig is. Of een bewoner heeft een parkeerboete ontvangen en moet die voor een bepaalde tijd betalen. Ook naar aanleiding van een product dat een inwoner of ondernemer heeft ontvangen, kunnen activiteiten door de inwoner of ondernemer nodig zijn. De activiteiten die een inwoner of ondernemer moet uitvoeren, noemen we taken.

Deze taken kunnen aan de inwoner of ondernemer onder andere worden aangeboden via een MijnOmgeving (en op termijn ook via MijnOverheid). De taken worden ‘klaargezet’ vanuit een zaakafhandelcomponent (ook wel vak- of procesapplicatie genoemd). De MijnOmgevingen en de zaakafhandelcomponenten moeten daarbij elkaar wel kunnen begrijpen. Om te voorkomen dat er meerdere ‘taken-standaarden’ door softwareleveranciers los van elkaar worden ontwikkeld, is de Taken-service door gemeenten en leveranciers samen ontworpen en beschreven.

De Taken-service is onderdeel van een breder dienstverleningsconcept. Het sluit aan bij de API Standaarden voor Zaakgericht Werken en past naadloos in een Omnichannel strategie. De Taken-service is zo beschreven dat deze ook overheidsbreed is toe te passen. Deze service geeft onder andere invulling aan de overheidsbrede interactieservices zoals deze zijn beschreven in de domeinarchitectuur Interactie als onderdeel van de Architectuur Digitale Overheid 2030.

# Businesswaarde

Dienstverlening aan burgers en ondernemers gebeurt steeds meer via de digitale weg. Overheidsorganisaties die hun interactieve dienstverlening digitaal aanbieden, kunnen transparanter zijn, sneller inspelen op behoefte van de inwoner of ondernemer, voorspelbaarder zijn in de afhandeling van verzoeken die binnenkomen en kunnen betere verantwoording afleggen over de geleverde dienstverlening. De Taken-service heeft daarin een belangrijke plaats. Door taken via een MijnOmgeving (en ook via MijnOverheid) aan te bieden, ontstaat een snellere afhandeling. Inwoners of ondernemers kunnen op elk gewenst moment van de dag de taak uitvoeren. Medewerkers worden op de hoogte gesteld als de taak is uitgevoerd of krijgen een signaal als de taak niet voor een bepaalde datum is uitgevoerd. De uitvoering van de processen en de verantwoording daarvan verloopt daardoor efficiënter omdat tijdverlies wordt verminderd.

![image.png](attachment:b5398dda-82c9-47d3-83c8-4c836cd8f08d:image.png)

Een voorbeeld is het kunnen uploaden van documenten die nodig zijn tijdens de behandeling van een zaak. Waar voorheen documenten via e-mail of op papier werden aangereikt, eventueel werden ingescand en door een medewerker handmatig aan de zaak moest worden gekoppeld, kan de inwoner of ondernemer de documenten direct uploaden via de MijnOmgeving waarna het document automatisch wordt opgeslagen en gekoppeld aan de zaak.

# Uitgangspunten

- De beschreven Taken-service is organisatie-, software- en leverancieronafhankelijk. Dat betekent dat de service overheidsbreed gebruikt kan worden en door verschillende leveranciers in verschillende software kan worden aangeboden.
- Een taak wordt geïnitieerd door de overheidsorganisatie richting de inwoner of ondernemer. Niet andersom.
- De externe taak is korte tijd in leven, alleen voor het ophalen/indienen van aanvullende informatie. Daarbij geldt een ingesteld handelingstermijn en een handelingsperspectief waarbinnen de taak moet worden uitgevoerd.
- Er wordt gebruik gemaakt van een Event Driven Architecture. Er treden events op als een taken worden geregistreerd of worden gewijzigd. Dat betekent dat het registratiecomponent waarin de registratie is vastgelegd (het Takenregistratiecomponent), verantwoordelijk is voor het versturen van een systeemnotificatie (publish van een event).
- Het beschreven patroon geldt vooralsnog alleen voor taken voor inwoners en ondernemers (externe taak). Een taak bedoeld voor een collega (bijvoorbeeld een terugbelnotitie) wordt gezien als een interne taak. Het patroon voor een interne taak wordt apart beschreven (to do).
- Een taak kan alleen worden uitgevoerd nadat is ingelogd via een erkend authenticatie en autorisatiemiddel. Vooralsnog is dat alleen DigiD of eHerkenning.
- Voor het tonen van een taak in een MijnOmgeving (of MijnOverheid) wordt gebruik gemaakt van NL Design System.