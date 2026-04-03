# Interactive Functionality

Ontwerp en maak voor een opdrachtgever een interactieve toepassing die voor iedereen toegankelijk is

De instructie vind je in: [INSTRUCTIONS.md](https://github.com/fdnd-task/the-web-is-for-everyone-interactive-functionality/blob/main/docs/INSTRUCTIONS.md)


## Inhoudsopgave

  * [Beschrijving](#beschrijving)
  * [Gebruik](#gebruik)
  * [Kenmerken](#kenmerken)
  * [Installatie](#installatie)
  * [Bronnen](#bronnen)
  * [Licentie](#licentie)

## Beschrijving
In dit project maak ik een webapp voor Bloemenveld Frankendael. In de repository [server-side-rendering-server-side-website](https://github.com/SebBastiaans/server-side-rendering-server-side-website) was begonnen aan dit project. In de sprint van deze repository draaide voornamleijk over een formulier maken die naar de database post. 

[Link naar mijn website.](https://the-web-is-for-everyone-interactive-mgem.onrender.com/)

## Gebruik
### Post functie
Adhv [deze user story](https://github.com/SebBastiaans/the-web-is-for-everyone-interactive-functionality/issues/9) heb ik een comment formulier gemaakt onder de nieuws pagina's. 


https://github.com/user-attachments/assets/0f286604-1e0c-4706-8a39-40079b731b91

### Algemene website
Verder kun je nu nieuwsartikelen op de homepagina zien, heeft de veldverkenner tab de juiste achtergrond, en heeft de collecite tab de 'in de bloei' en 'na de bloei' keuze.


https://github.com/user-attachments/assets/24db2700-62b1-4df1-89f0-a65f61ea1b44



## Kenmerken
### POST functie
HTML
https://github.com/SebBastiaans/the-web-is-for-everyone-interactive-functionality/blob/d59660f44eede4bc007a9688d771f1e4236652c0/views/partials/commentForm.liquid#L1-L25
CSS
https://github.com/SebBastiaans/the-web-is-for-everyone-interactive-functionality/blob/d59660f44eede4bc007a9688d771f1e4236652c0/public/styles/partials.css#L66-L160
javaScript
https://github.com/SebBastiaans/the-web-is-for-everyone-interactive-functionality/blob/d59660f44eede4bc007a9688d771f1e4236652c0/server.js#L107-L158

Met bovenstaande code heb ik een werkend formulier gemaakt. Uitleg hoe het werkt:
Iemand voert op de website informatie in het formulier in. Door de 'name' in de [HTML elementen](https://github.com/SebBastiaans/the-web-is-for-everyone-interactive-functionality/blob/d59660f44eede4bc007a9688d771f1e4236652c0/views/partials/commentForm.liquid#L7-L9) wordt deze informatie juist gelinkt, [opgehaald in de server.js](https://github.com/SebBastiaans/the-web-is-for-everyone-interactive-functionality/blob/d59660f44eede4bc007a9688d771f1e4236652c0/server.js#L139-L143) en omgezet in JSON. Dan wordt je doorgestuurd naar de juiste pagina. In de GET route wordt er data uit de database [gefetched](https://github.com/SebBastiaans/the-web-is-for-everyone-interactive-functionality/blob/d59660f44eede4bc007a9688d771f1e4236652c0/server.js#L112), [gefiltered](https://github.com/SebBastiaans/the-web-is-for-everyone-interactive-functionality/blob/d59660f44eede4bc007a9688d771f1e4236652c0/server.js#L116-L120), [omgezet ](https://github.com/SebBastiaans/the-web-is-for-everyone-interactive-functionality/blob/d59660f44eede4bc007a9688d771f1e4236652c0/server.js#L113) en [gerendered](https://github.com/SebBastiaans/the-web-is-for-everyone-interactive-functionality/blob/d59660f44eede4bc007a9688d771f1e4236652c0/server.js#L125-L131) om het in Liquid te kunnen gebruiken. Door een [for loop in Liquid](https://github.com/SebBastiaans/the-web-is-for-everyone-interactive-functionality/blob/d59660f44eede4bc007a9688d771f1e4236652c0/views/partials/commentForm.liquid#L15-L23) wordt de data gebruikt en de code steeds herhaald. 
<img width="386" height="422" alt="image" src="https://github.com/user-attachments/assets/3e8c290a-f3c4-41d8-aee7-56cb29b2bfd2" />


### States POST functie
BIj het doorsturen van data wordt er bij de database [gecheckt of dit lukt of niet](https://github.com/SebBastiaans/the-web-is-for-everyone-interactive-functionality/blob/d59660f44eede4bc007a9688d771f1e4236652c0/server.js#L150). Voor [beide uitkomsten](https://github.com/SebBastiaans/the-web-is-for-everyone-interactive-functionality/blob/d59660f44eede4bc007a9688d771f1e4236652c0/server.js#L150-L158) is er een andere weg. Dan wordt er bij [de GET gevraagd](https://github.com/SebBastiaans/the-web-is-for-everyone-interactive-functionality/blob/d59660f44eede4bc007a9688d771f1e4236652c0/server.js#L129-L130) of het 'mislukt' of 'gelukt' is. En wordt er 'error' of 'gelukt' meegegven bij het renderen. [In Liquid](https://github.com/SebBastiaans/the-web-is-for-everyone-interactive-functionality/blob/d59660f44eede4bc007a9688d771f1e4236652c0/views/partials/commentForm.liquid#L4) wordt er dan gekeken of deze 'error' of 'gelukt' wordt verkregen, en dan de passende class doorgegeven. Deze class heeft dan [verschillende styling](https://github.com/SebBastiaans/the-web-is-for-everyone-interactive-functionality/blob/d59660f44eede4bc007a9688d771f1e4236652c0/public/styles/partials.css#L163-L191) voor de states. Dat ziet er zo uit of de website:
<img width="399" height="444" alt="image" src="https://github.com/user-attachments/assets/acdd4da4-77f7-4d15-9749-b6dacfa4a640" />
<img width="399" height="436" alt="image" src="https://github.com/user-attachments/assets/7965dee9-ac74-4d49-89c4-0da5c9fc8fbc" />


### Browsers getest
In [dit issue](https://github.com/SebBastiaans/the-web-is-for-everyone-interactive-functionality/issues/21) heb ik de website met functies getest.

## Installatie
<!-- Bij Installatie staat hoe een andere developer aan jouw repo kan werken -->
Om te kunnen werken aan deze repo moet je dit eerst doen:
- clone de repository naar je editor
- doe in je terminal 'npm install' en dan 'npm run start'

## Bronnen

## Licentie

This project is licensed under the terms of the [MIT license](./LICENSE).
