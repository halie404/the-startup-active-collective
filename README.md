# Ontdek de Schoonmaak – Vacaturepagina

> **English summary:** A responsive, mobile-first job listings page I built for a real client, *Ontdek de Schoonmaak*, an online job board for the cleaning industry. The assignment came from the digital agency Active Collective (Beverwijk). I turned a desktop-only Figma design into a mobile-first website using HTML, CSS and vanilla JavaScript, with a working filter menu and accessible navigation.

**[Bekijk de live versie](https://ontdekdeschoonmaak.netlify.app/)**

<p>
  <a href="https://github.com/user-attachments/assets/304a29a9-cf40-4606-b117-afa55fb56190">
    <img src="https://github.com/user-attachments/assets/304a29a9-cf40-4606-b117-afa55fb56190" alt="Vacaturepagina van Ontdek de Schoonmaak op desktop" width="800" />
  </a>
</p>

## Inhoudsopgave

- [Beschrijving](#beschrijving)
- [Kenmerken](#kenmerken)
- [Responsive design](#responsive-design)
- [Filters](#filters)
- [Interactiviteit en feedback](#interactiviteit-en-feedback)
- [Toegankelijkheid](#toegankelijkheid)
- [Gebruikte technieken](#gebruikte-technieken)
- [Wat ik heb geleerd](#wat-ik-heb-geleerd)
- [Beperkingen en vervolgstappen](#beperkingen-en-vervolgstappen)
- [Lokaal draaien](#lokaal-draaien)
- [Projectstructuur](#projectstructuur)
- [Credits](#credits)

## Beschrijving

Active Collective is een digital agency uit Beverwijk die bedrijven helpt hun online aanwezigheid te verbeteren. Voor hun klant *Ontdek de Schoonmaak* kreeg ik de opdracht om een vacaturewebpagina te bouwen.

*Ontdek de Schoonmaak* is een schoonmaakbedrijf dat nieuw personeel zoekt. Steeds meer mensen bekijken vacatures via hun telefoon, dus de pagina moest net zo goed werken op mobiel als op desktop.

Het ontwerp kwam uit Figma en was alleen voor desktop gemaakt. Mijn opdracht was om dit om te zetten naar een mobielvriendelijke versie, met de focus op een mobile-first ontwerp waarmee gebruikers makkelijk vacatures kunnen filteren op locatie, functie en andere voorkeuren.

## Kenmerken

- Mobile-first ontwerp
- Filtermenu voor eenvoudige zoekfunctionaliteit
- Gebruiksvriendelijke interface voor zowel desktop als mobiel
- Hamburgermenu op mobiel en tablet, horizontaal menu op desktop
- Vacaturekaarten met datum, plaats, uren per week en salaris

## Responsive design

De website is volledig responsief en wordt optimaal weergegeven op desktop, tablet en mobiel. Ik heb mobile-first gewerkt: de basisstijlen gelden voor kleine schermen en grotere schermen breiden die uit met `min-width` media queries.

| Schermbreedte | Vacatures | Navigatie | Filters |
| --- | --- | --- | --- |
| Tot 639px (mobiel) | 1 kolom | Hamburgermenu | Openklapbaar paneel, onder elkaar |
| 640px – 1023px (tablet) | 2 kolommen | Hamburgermenu | Openklapbaar paneel, 2 kolommen |
| 1024px en groter (desktop) | 3 kolommen | Horizontaal menu | Altijd zichtbaar, keuzelijsten onder de knoppen |

Verder:

- Het lettertype schaalt mee met de schermbreedte via `clamp()`
- De kaarten gebruiken CSS subgrid, zodat titels, details en knoppen op één lijn staan
- De inhoud heeft een maximale breedte, zodat de pagina op grote schermen leesbaar blijft

<p>
  <a href="https://github.com/user-attachments/assets/0315f00f-5cf9-4e34-9545-494053664aa0">
    <img src="https://github.com/user-attachments/assets/0315f00f-5cf9-4e34-9545-494053664aa0" alt="Dezelfde pagina op mobiel, tablet en desktop naast elkaar" width="800" />
  </a>
  <br />
  <em>Mobiel, tablet en desktop</em>
</p>

<p>
  <a href="https://github.com/user-attachments/assets/c27932f5-b8d5-4b61-8a63-37426e2d10f7">
    <img src="https://github.com/user-attachments/assets/c27932f5-b8d5-4b61-8a63-37426e2d10f7" alt="Mobiele weergave met het hamburgermenu geopend" width="300" />
  </a>
  <br />
  <em>Hamburgermenu op mobiel</em>
</p>

## Filters

Een belangrijk onderdeel van de vacaturepagina is het filtermenu. Gebruikers kunnen filteren op:

- Vakgebied
- Werkomgeving
- Type werk (fulltime, parttime, stage)
- Afstand (vanaf een plaats, tot een maximale afstand)
- Salaris

Het filtermenu is ontworpen om gemakkelijk toegankelijk en intuïtief te zijn, zelfs op mobiele apparaten. Het is gebouwd met `<details>`-elementen, een dropdown-menu en checkboxes. De vacaturelijst wordt direct bijgewerkt zodra de gebruiker iets selecteert.

- Opties binnen één filter werken als "of", verschillende filters samen werken als "en"
- Een teller toont hoeveel vacatures overblijven
- Een filter dat in gebruik is krijgt een kleur en een teller
- "Filters wissen" verschijnt zodra er een filter actief is
- Als er geen resultaten zijn, krijgt de gebruiker daar een melding van

<p>
  <a href="https://github.com/user-attachments/assets/e61311ba-9596-4066-aa1d-485c9af8e81c">
    <img src="https://github.com/user-attachments/assets/e61311ba-9596-4066-aa1d-485c9af8e81c" alt="Filter geopend op desktop" width="800" />
  </a>
  <br />
  <em>Filter op desktop</em>
</p>

<p>
  <a href="https://github.com/user-attachments/assets/b8848ce4-488f-4e81-a475-916c0b6f08de">
    <img src="https://github.com/user-attachments/assets/b8848ce4-488f-4e81-a475-916c0b6f08de" alt="Actieve filters met kleur en teller" width="800" />
  </a>
  <br />
  <em>Actieve filters met teller</em>
</p>

<p>
  <a href="https://github.com/user-attachments/assets/f3bfb272-9b09-40f8-96e5-6b7852f12c1b">
    <img src="https://github.com/user-attachments/assets/f3bfb272-9b09-40f8-96e5-6b7852f12c1b" alt="Filterpaneel op mobiel" width="300" />
  </a>
  <br />
  <em>Filter op mobiel</em>
</p>

## Interactiviteit en feedback

De website gebruikt verschillende interactieve elementen om de gebruikerservaring te verbeteren:

- **Hover-effecten** op knoppen, kaarten en filters geven visuele feedback, zodat duidelijk is welke elementen klikbaar zijn
- **Feedback bij het filteren:** wanneer een gebruiker een filter toepast, worden de resultaten onmiddellijk bijgewerkt zonder dat de pagina opnieuw wordt geladen, zodat de interactie niet zonder reactie blijft

<p>
  <a href="https://github.com/user-attachments/assets/89cb64d1-8129-4440-9a37-df953c29bd73">
    <img src="https://github.com/user-attachments/assets/89cb64d1-8129-4440-9a37-df953c29bd73" alt="Hover- en focusstatus van een vacaturekaart" width="400" />
  </a>
  <br />
  <em>Hover- en focusstatus</em>
</p>

## Toegankelijkheid

- Semantische HTML (`header`, `nav`, `main`, `section`, `article`, `footer`)
- Zichtbare focusstijl voor toetsenbordgebruikers
- `aria-expanded` en `aria-controls` op de menu- en filterknoppen
- Het menu sluit met de Escape-toets
- De resultaatteller gebruikt `aria-live`, zodat schermlezers wijzigingen horen
- Animaties worden uitgeschakeld voor gebruikers met `prefers-reduced-motion`

## Gebruikte technieken

- **HTML5**: semantische structuur
- **CSS3**: custom properties, Grid, Flexbox, subgrid, `clamp()` en media queries
- **JavaScript (vanilla)**: DOM-manipulatie, event listeners en filterlogica
- **Figma**: ontwerp van de klant
- **Git en GitHub**, gepubliceerd via Netlify

## Wat ik heb geleerd

- Een desktopontwerp omzetten naar een mobile-first website
- Een filtermenu bouwen dat goed werkt op telefoon, tablet en desktop
- Werken voor een echte klant en een ontwerp vertalen naar werkende code
- Interactie en feedback in een interface ontwerpen, zoals hover-effecten en directe filterresultaten

## Beperkingen en vervolgstappen

- De vacatures staan als statische HTML. Met een backend of API worden ze dynamisch.
- Het afstandsfilter werkt met een vaste lijst van Nederlandse plaatsen en rekent hemelsbreed. Postcodes vragen een geocoding-dienst, bijvoorbeeld de PDOK Locatieserver.
- Het salarisfilter gebruikt een geschat maandbedrag, berekend uit uurloon en uren per week.
- De knop "Bekijk vacature" verwijst nog niet naar een detailpagina.

## Lokaal draaien

```bash
git clone https://github.com/halie404/the-startup-active-collective.git
cd the-startup-active-collective
```

Open `index.html` in je browser, of gebruik een lokale server, bijvoorbeeld de Live Server-extensie in VS Code.

## Projectstructuur

```text
.
├── assets/                    Afbeeldingen en iconen
├── styles/
│   ├── active-collective.css  Kleuren, lettertypes en afmetingen (variabelen)
│   └── styles.css             Opmaak van de pagina
├── index.html
├── script.js                  Menu, filters en afstandsfilter
└── README.md
```

- Opdrachtgever: Ontdek de Schoonmaak (OSB Holding BV)
- Opdracht via: Active Collective, Beverwijk
- Logo en huisstijl zijn eigendom van de opdrachtgever.
