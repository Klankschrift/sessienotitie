# Handleiding

Alles over het dagelijks werken met Sessienotitie: van voorbereiden en opnemen tot bijsturen,
supervisie, kopiëren en wat te doen als iets niet lukt. Heb je de app nog niet werkend? Begin
dan bij **[In vier stappen aan de slag](README.md#in-vier-stappen-aan-de-slag)** in de README.

## Inhoud

- [Zo werk je ermee](#zo-werk-je-ermee)
  1. [Voor het gesprek — voorbereiden](#1-voor-het-gesprek--voorbereiden)
  2. [Opnemen (of uploaden)](#2-opnemen-of-uploaden)
  3. [Wat er daarna vanzelf gebeurt](#3-wat-er-daarna-vanzelf-gebeurt)
  4. [Bijsturen](#4-bijsturen)
  5. [Supervisie](#5-supervisie)
  6. [Kopiëren en controleren](#6-kopiëren-en-controleren)
  7. [Sneltoetsen](#7-sneltoetsen)
- [Goed om te weten](#goed-om-te-weten)
- [Problemen oplossen](#problemen-oplossen)

---

## Zo werk je ermee

### 1. Voor het gesprek — voorbereiden

Bovenaan, in **Voorbereiding**, staat alles wat per gesprek verschilt:

| Veld | Waarvoor |
|---|---|
| **Type gesprek** | Intake- of behandelgesprek. Bepaalt de opbouw van het verslag: een intake krijgt de klassieke intake-kopjes, een behandelgesprek kiest zijn eigen indeling. |
| **Geslacht cliënt** | Zodat het verslag de juiste voornaamwoorden gebruikt. Laat je dit op "Niet opgegeven", dan schrijft het model neutraal. |
| **Voorinformatie (optioneel)** | Achtergrond die het model mag meenemen: uitkomsten van een vragenlijst, een eerder gespreksverslag. Standaard gebruikt het model dit alleen om het gesprek beter te begrijpen; het verslag blijft over dít gesprek gaan. Vink **"Voorinformatie ook in het verslag opnemen"** aan als de informatie zelf in het verslag hoort — bijvoorbeeld vragenlijstscores bij een intake. |
| **Behandeldoel (optioneel)** | Plak hier het behandeldoel uit het dossier. Het gaat alleen naar de supervisie, die erop terugkijkt hoe doelgericht het gesprek was (zie stap 5). |
| **Extra instructie (optioneel)** | Losse aanwijzingen voor dit ene gesprek, bijvoorbeeld *"Er waren meerdere gesprekspartners aanwezig"* of *"Richt je vooral op de bespreking van de thuisopdracht."* |

Zodra er een transcript staat, klapt de voorbereiding vanzelf dicht; de kop laat dan zien
wat er is ingevuld.

Links, in het ingeklapte paneel **Instellingen**, staat wat je eenmalig kiest. Dichtgeklapt
zie je in de kop welk model en welk formaat gekozen zijn:

- **Taalmodel** — standaard **Mistral Large 3**. **Large 4, met nadenken** is een proef:
  het denkt eerst na en schrijft dan, wat duidelijk langer duurt. Large 4 zonder nadenken
  zit er bewust niet in: dat nam fouten van de spraakherkenning letterlijk over en verzon er
  een uitleg bij, en zette losse Engelse en Duitse woorden in de tekst.
- **Uitvoerformaat (kopiëren)** — platte tekst, ruwe Markdown of opgemaakte (HTML) tekst.
  Kies wat je dossiersysteem het beste aankan; achteraf wisselen mag ook.
- **Emoji bij kopjes** — maakt het verslag sneller scanbaar. Zet uit als je dossier daar
  niet van houdt.
- **Supervisie** — laat het model in een apart venster meedenken (zie stap 5).
- **Titel verzinnen** — een korte omschrijving van het gespreksonderwerp boven het verslag.

De keuzes blijven bewaard voor de volgende keer; wat je in de tekstvelden typt niet. De
**microfoonkeuze** staat bij **Opname** — daar hoort hij bij.

### 2. Opnemen (of uploaden)

Kies bij **Opname** je bron:

- **🎙 Microfoon** — voor een gesprek in de spreekkamer. Klik op de ronde knop om te
  starten, en nogmaals om te stoppen. De teller loopt mee. Met het toetsenbord (`Spatie`,
  `R` of `Esc`) vraagt stoppen een tweede druk binnen drie seconden: stoppen is definitief,
  en een map op het toetsenbord mag een gesprek niet afbreken.
- **🖥 Scherm** — voor een online gesprek. Je browser vraagt wat je wilt delen:
  kies een **tabblad** of **venster** en **vink "Audio delen" aan**. Volledig-scherm delen
  levert op veel systemen geen audio op. Je eigen microfoon wordt automatisch bijgemengd,
  zodat beide kanten van het gesprek worden opgenomen. Het beeld wordt niet gebruikt: het
  videospoor gaat meteen uit, er wordt alleen geluid opgenomen.
- **📋 Transcript plakken** — heb je het gesprek al ergens anders laten uitwerken, plak
  het transcript dan rechtstreeks in het transcriptveld (sneltoets `P`) en klik op
  **Verslag maken** (of `Ctrl`+`Enter`). Opnemen is dan niet nodig.
- **📁 Audiobestand kiezen…** — heb je al een opname, upload die dan (`.mp3`, `.m4a`,
  `.wav`, `.ogg`, `.opus`, `.flac`, `.webm`, `.mp4`). Een videobestand mag ook; lukt dat
  niet, zet het dan eerst om naar `.mp3` of `.wav`. Uploaden werkt in elke browser, ook in
  Safari en Firefox.

Tijdens de opname zie je een **golfbeeld en niveaumeters**, zodat je ziet dát er geluid
binnenkomt — met een waarschuwing als een bron tien seconden stil blijft.

### 3. Wat er daarna vanzelf gebeurt

De stappen **Opname → Transcriptie → Verslag** in de kopbalk houden je op de hoogte:

1. De audio gaat naar Voxtral en het **transcript** verschijnt, met sprekers gelabeld als
   "Spreker 1", "Spreker 2", …
2. Het **verslag** wordt meteen daarna geschreven en verschijnt al typend in beeld.
3. Zodra het klaar is, staat het verslag **automatisch op je klembord**. Je hoeft dus niet
   eens op een knop te drukken als je het meteen wilt plakken. Het transcript schuift dan
   als naslag onder verslag en supervisie, ingeklapt tot één regel; met **Tonen** haal je
   het terug.

Tegelijk met het verslag kijkt een aparte aanroep of er iets ter sprake kwam dat de
**veiligheid** raakt: gedachten aan de dood of zelfdoding, zelfbeschadiging, geweld,
zorgen om kinderen, ernstige verwaarlozing of gevaarlijk gedrag door psychose of middelen —
ook als het werd uitgevraagd en ontkend. Is er iets, dan staat er boven het verslag een
melding, met per signaal **Toon in transcript**. Is er niets, dan zie je niets. Mislukt de
controle, dan staat dat er wel, met **Opnieuw proberen**. Deze controle loopt altijd op
Mistral Large 3, ook als je een ander taalmodel kiest: een gemist signaal is precies de
fout waarvoor hij bestaat.

### 4. Bijsturen

Klopt het verslag niet helemaal? Ligt het aan de spraakherkenning (een verkeerd verstane
naam, een verwisselde spreker), verbeter dan eerst het **transcript**: klik erin (met
**Tonen** haal je het terug als het is ingeklapt), pas het aan en klik op **Verslag opnieuw
maken**. Daarmee komen ook supervisie en veiligheidscontrole opnieuw. Ligt het aan het
verslag zelf, dan zijn er drie manieren:

- **Zelf aanpassen** — klik in het verslag en typ. Kopiëren, de sectieknoppen en
  herzien nemen je wijziging mee. Opmaak toevoegen kan niet (er is geen werkbalk), Enter
  geeft een nieuwe alinea of een nieuw punt, en plakken komt binnen als platte tekst.
- **↻ Opnieuw genereren** — zelfde transcript, met de instellingen zoals ze nu staan.
  Heb je sinds het verslag iets veranderd (gesprekstype, geslacht, taalmodel, een vinkje),
  dan zegt de knop **"met nieuwe instellingen"** en noemt de tooltip wat er anders is.
- **Verslag herzien** — je typt in gewone taal wat er anders moet, bijvoorbeeld
  *"Werk de afspraken explicieter uit, elk met een eigen kopje, in plaats van ze samen te
  vatten."* Het verslag wordt dan **opnieuw uit het transcript geschreven** met jouw
  aanwijzing erbij; het wordt dus niet ter plekke bijgewerkt. Dat is bewust: zo blijft het
  verslag als geheel kloppen in plaats van een lappendeken te worden. Wél houdt het model
  de vorige versie ernaast, zodat wat goed was blijft staan.

  > Je eigen bewerkingen gaan mee als de vorige versie, maar het verslag wordt wel opnieuw
  > geschreven: controleer daarna of je correcties zijn blijven staan.

Wil je weten waarop een zin rust? **Selecteer een stuk van het verslag**, en er verschijnt
een knopje **Waar staat dit?**. Dat zoekt (met Mistral Small 4) de plek in het transcript,
klapt het transcript open en markeert de passage. Staat iets er maar deels of niet, dan
zegt de melding boven het transcript wat er anders staat: een getal, een verband, een
richting. `Esc` of het kruisje haalt de markering weg.

Elke keer dat je opnieuw genereert of herziet, komt er een **versie** bij. Verschijnen de
versiepijltjes in de kop van het verslag, dan kun je met **←** en **→** heen en weer bladeren; erachter staat welke
aanwijzing die versie opleverde. Herzien gaat verder vanaf de versie die je op dat moment
bekijkt, en de nieuwe versie komt altijd achteraan. Elke versie die je bekijkt, wordt
meteen naar het klembord gekopieerd.

### 5. Supervisie

Staat het vinkje aan, dan verschijnt onder het verslag een apart venster met de blik van
een supervisor op het gesprek:

- **Onuitgesproken** — iets wat er lijkt te liggen maar niet op tafel komt, vastgemaakt aan
  een moment in het gesprek en geschreven als vraag of vermoeden.
- **Doelgerichtheid** — opbouwende feedback op hoe het gesprek bijdroeg aan het doel, ook
  wat goed ging. Vul je een **behandeldoel** in, dan is dat de maat; zonder doel leidt de
  supervisor het af uit het gesprek. Bij een intake is het doel de hulpvraag helder krijgen,
  en hoort luisteren daar gewoon bij.
- De **roos van Leary** — een plaatje van hoe iedere gesprekspartner zich in dit gesprek
  tegenover de ander opstelde, met per persoon de momenten waarop dat rust.

Daaronder staat de knop **Tips voor het gesprek**. Die vraagt, voortbouwend op wat de
supervisor zag, wat je in een volgend gesprek anders kunt doen: hoe je naar je
voorkeurspositie op de roos beweegt, hoe je de cliënt uitnodigt tot de zijne, en hoe je het
onuitgesprokene ter sprake kunt brengen. De voorkeursposities verschillen per gesprekstype:
in een behandelgesprek ben jij helpend en de cliënt meewerkend; in een intake luister jij
vooral (meewerkend tot volgend) en neemt de cliënt de leiding.

Supervisie en tips spreken je aan met 'je' en verwijzen nooit met 'hij' of 'zij' naar de
behandelaar. Het zijn eigen aanroepen naast het verslag, en de tekst is voor jou: hij gaat
**nooit mee in wat je kopieert** — daar is dat aparte venster voor.

### 6. Kopiëren en controleren

Onder het verslag staat één knop, **Kopiëren** (sneltoets `C`): het verslag met de titel,
zonder de tip. Bij een **intake** krijgt daarnaast elke sectiekop een eigen knopje
**Kopiëren**, dat alleen de inhoud van die sectie op het klembord zet — zónder de kopregel,
want het veld in het dossier draagt die naam zelf al. Zo'n knop blijft daarna aangevinkt
staan, zodat je in een lange intake ziet welke velden je al hebt overgenomen.

Het **uitvoerformaat** uit Instellingen bepaalt wat er op het klembord komt; wissel je het
achteraf, dan wordt er meteen opnieuw gekopieerd.

Onder het verslag, ingeklapt, staat **Brief, samenvatting of huiswerk voor de cliënt**: een
brief aan de huisarts of verwijzer, een samenvatting voor de cliënt in eenvoudige taal (B1)
met de afspraken, of alleen het huiswerk — wat de cliënt tot het volgende gesprek gaat doen,
zonder de datum van de volgende afspraak (die komt via de agenda). Alle drie worden
geschreven uit **het verslag zoals het er staat**, met je eigen aanpassingen, en niet uit
het transcript: zo kan er geen feit bij komen dat het verslag niet heeft. De tekst is
bewerkbaar en wordt gekopieerd in het gekozen uitvoerformaat. Lees hem na voordat je hem
verstuurt.

> **Controleer het verslag altijd** voordat je het in het dossier plakt. Transcriptie en
> taalmodellen maken fouten; de inhoudelijke verantwoordelijkheid blijft bij jou.

Met **Nieuw gesprek** maak je het scherm leeg voor de volgende sessie. Staat er nog werk,
dan vraagt de knop eerst om een bevestiging.

### 7. Sneltoetsen

Buiten de tekstvelden bedien je de app met het toetsenbord. Het volledige overzicht staat
achter de toetsenbordknop rechtsboven, of achter **?**:

| Toets | Wat het doet |
|---|---|
| `Spatie` of `R` | Opname starten, of twee keer: stoppen |
| `Esc` | Twee keer: opname stoppen (of het overzicht sluiten, of een markering weghalen) |
| `U` | Audiobestand kiezen |
| `P` | Naar het transcriptveld — plakken of bijschaven |
| `Ctrl`+`Enter` (in het transcriptveld) | Verslag maken uit het transcript |
| `C` | Verslag kopiëren |
| `T` | Transcript kopiëren |
| `G` | Opnieuw genereren |
| `H` | Naar het veld "Verslag herzien" |
| `Ctrl`+`Enter` (in het herzieningsveld) | Herziening versturen |
| `←` `→` | Vorige of volgende versie |
| `V` / `I` | Naar voorinformatie / extra instructie |
| `N` | Nieuw gesprek |
| `D` | Donker of licht |
| `?` | Dit overzicht |

---

## Goed om te weten

- **Van het gesprek zelf wordt zo weinig mogelijk bewaard.** Transcript, verslag, tip en
  versies bestaan alleen in het geheugen van dit tabblad. Ververs je de pagina of sluit je
  hem, dan zijn die weg. **Kopieer je verslag dus voordat je afsluit.** Probeer je een
  tabblad met een lopende opname of een transcript erin te sluiten, dan waarschuwt de
  browser je eerst.
- **De opname zelf heeft een vangnet.** Zodra je stopt, zet de pagina een reservekopie van
  de audio in de opslag van de browser (IndexedDB, op je schijf). De kopie verdwijnt zodra
  er een verslag van is, als je hem weggooit, bij **Nieuw gesprek**, en anders zodra je het
  tabblad sluit (de browser waarschuwt eerst). Alleen na een crash van browser of computer
  staat de opname er bij het volgende openen nog, om alsnog te verwerken of te downloaden.
- **Een wegvallende microfoon hoor je meteen, en de opname loopt door.** Valt de verbinding
  met de microfoon weg (bijvoorbeeld een Bluetooth-headset), dan klinkt er één zacht
  pingetje op het standaardgeluidsapparaat van je computer, met een rode balk en een
  knipperende tabtitel die blijven staan tot je ze uitzet. Stilte in het gesprek geeft
  geen alarm. De opname loopt intussen door; verbind de microfoon opnieuw en klik op
  **Vervolgen** onder de opnameknop. Het blijft één opname met één transcript, dus de
  sprekerlabels blijven kloppen; het ontbrekende stuk wordt gemeld met begin- en eindtijd.
- **Je keuzes blijven wél bewaard**, in deze browser: type gesprek, taalmodel,
  uitvoerformaat, microfoonkeuze, opnamebron, de vinkjes, of de instellingen openstaan, en
  licht of donker. Cliëntinhoud nadrukkelijk niet — voorinformatie, behandeldoel, extra
  instructie, transcript, verslag en documenten gaan nooit naar de opslag van de browser. Het geslacht van de cliënt hoort daar ook bij
  en staat na het herladen weer op "Niet opgegeven".
- **`Nieuw gesprek` maakt niet alles leeg.** Transcript, verslag, supervisie, versies,
  veiligheidsmelding, documenten, geslacht, voorinformatie, behandeldoel en extra instructie
  worden gewist; het gesprekstype, het taalmodel, de drie vinkjes en je API-sleutel blijven
  staan — meestal precies wat je wilt bij een volgende cliënt.
- **De app vraagt bij het openen meteen microfoontoestemming.** Dat is nodig om de
  keuzelijst met microfoons te kunnen tonen; er wordt op dat moment niets opgenomen.
- **Zie je `[herhalingsfout in transcript]` staan?** Dan zat de spraakherkenning even in
  een herhalingslus (een bekend verschijnsel bij onduidelijke audio). De app haalt die lus
  eruit en zet er een markering neer, zodat het verslag er niet door in de war raakt.
- **Echo-onderdrukking, ruisonderdrukking en automatische volumeregeling staan bewust uit.**
  Die functies zijn gemaakt voor bellen en knippen bij een tweegesprek juist stukken uit de
  stem van de ander; zonder die filters wordt het transcript beter.
- **Welke modellen de app gebruikt.** `voxtral-mini-latest` voor de transcriptie; voor
  verslag, supervisie, tips en documenten het taalmodel uit de instellingen (standaard
  Mistral Large 3, `mistral-large-2512`, op zijn vaste naam: `mistral-large-latest` verhuist
  vroeg of laat naar Large 4). De veiligheidscontrole loopt altijd op Large 3, en **Waar
  staat dit?** op Mistral Small 4 (`mistral-small-2603`): dat is zoeken en aanwijzen, geen
  schrijven.
- **Het verkeer gaat naar het Europese endpoint** van Mistral, `api.eu.mistral.ai`. Je
  aanvragen verlaten de EU dus niet.
- **Op een telefoon blijft het scherm aan zolang je opneemt.** Zonder dat valt de opname
  stil zodra het scherm uitgaat. Weigert je toestel dat (bijvoorbeeld door
  batterijbesparing), dan loopt de opname gewoon door — houd het scherm dan zelf wakker.

---

## Problemen oplossen

| Wat je ziet | Wat je doet |
|---|---|
| **"Geen API-sleutel"** | Plak je sleutel in het paneel linksboven en klik op **Opslaan**. Zonder sleutel kun je niet opnemen of uploaden. |
| **Microfoonlijst zegt "Toegang geweigerd"** | Geef in je browser toestemming voor de microfoon (het slotje of camera-icoontje in de adresbalk) en **herlaad de pagina**. |
| **"Geen audio gedeeld"** bij schermdelen | Je hebt het deelvenster bevestigd zonder **"Audio delen"** aan te vinken. Probeer opnieuw en kies een **tabblad** of **venster** — bij volledig scherm biedt de browser vaak geen audio aan. |
| **"Mistral API-sleutel is ongeldig of ontbreekt"** | De sleutel klopt niet (meer). Maak een nieuwe aan op [console.mistral.ai/api-keys](https://console.mistral.ai/api-keys) en sla die op. |
| **"Mistral API-limiet bereikt"** | Je zit tegen een snelheidslimiet aan. Wacht even en probeer het opnieuw. |
| **"Mistral kon de aanvraag niet verwerken"** | Meestal een audiobestand in een formaat dat Voxtral niet aankan. Zet het om naar `.mp3` of `.wav` en probeer opnieuw. |
| **"Mistral antwoordde met status …"** | Vaak een ontbrekende betaalmethode of een tijdelijke storing. Controleer je account op [console.mistral.ai](https://console.mistral.ai) en probeer het later nog eens. |
| **"Opname starten mislukt: …"** | Meestal een geweigerde microfoon (zie hierboven), of een andere toepassing die het apparaat vasthoudt. |
| **De opname valt stil op de telefoon** | De app houdt het scherm aan tijdens de opname, maar batterijbesparing kan dat blokkeren. Zet batterijbesparing uit, of houd het scherm zelf aan. |
| **Schermdeling geeft geen geluid in Firefox of Safari** | Die browsers delen geen tabbladaudio. Gebruik Chrome of Edge voor online gesprekken. |
| **Het gedownloade bestand opent als tekst** | De bestandsnaam eindigt niet op `.html`. Hernoem het bestand (bijvoorbeeld `sessienotitie.html`) en open het opnieuw. |
| **Je sleutel is na het herladen weg** | Je zit in een privé- of incognitovenster, of je browser wist site-gegevens bij afsluiten. Gebruik een gewoon venster. |
| **Het verslag klopt inhoudelijk niet** | Een woord of zin pas je zelf aan in het verslag. Moet er meer anders, gebruik dan **Verslag herzien** en zeg in gewone taal wat er anders moet. Twijfel je waar iets vandaan komt, selecteer het dan en klik op **Waar staat dit?**. Blijft het misgaan, controleer dan het transcript — bij slechte audio valt er weinig te redden. |
| **Alles is weg na het herladen** | Transcript en verslag worden niet bewaard (zie [Goed om te weten](#goed-om-te-weten)); kopieer het verslag voortaan vóór je de pagina verlaat. Een opname waar nog geen verslag van was, staat bovenaan klaar om opnieuw te verwerken. |

---

Meer lezen: wat het kost en hoe je begint staat in de **[README](README.md)**; wat er met de
gegevens gebeurt en waar je zelf voor verantwoordelijk blijft, staat in
**[PRIVACY.md](PRIVACY.md)**.
