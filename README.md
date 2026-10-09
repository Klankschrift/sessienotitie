# Sessienotitie

Een gespreksverslag-hulpmiddel voor psychologen en andere behandelaars, dat volledig in
de browser draait. Je neemt een gesprek op (of uploadt een audiobestand), waarna het
automatisch wordt **getranscribeerd** en omgezet in een gestructureerd, professioneel
**dossierverslag** dat je daarna kunt bijsturen tot het klopt. Alles verloopt via je
**eigen Mistral API-sleutel** — er is geen server en geen account bij de maker nodig.

Het hele programma is één bestand: `index.html`.

> 🧪 **Experimenteel project.** Dit is een vrij, open-source **experiment** — geen
> commercieel product, zonder ondersteuning, garanties of toezeggingen. Het wordt
> aangeboden zoals het is, zodat iedereen het kan bekijken, gebruiken en aanpassen. Of het
> voor jouw situatie geschikt en toelaatbaar is, beoordeel je zelf.

> 🔒 **Minimumvereiste voor cliëntgegevens: Zero Data Retention (ZDR).** Gebruik dit voor
> échte cliëntgesprekken **alleen als je bij Mistral ZDR hebt aangevraagd en het aanstaat**.
> Zonder ZDR bewaart Mistral je gegevens standaard ongeveer 30 dagen — dat is voor
> gezondheidsgegevens niet acceptabel; gebruik de app dan alleen met niet-herleidbare
> oefengesprekken. Hoe je ZDR aanvraagt, staat bij
> [Stap 1](#stap-1--account-betaling-en-zero-data-retention).
>
> En zelfs **mét** ZDR ben je er niet automatisch: ZDR is *noodzakelijk maar niet
> voldoende* voor NEN 7510. Lees eerst **[PRIVACY.md](PRIVACY.md)** — dit is een
> hulpmiddel, geen kant-en-klare NEN 7510-conforme oplossing, en gebruik is voor eigen
> verantwoordelijkheid en risico.

---

## Inhoud

- [Wat het doet](#wat-het-doet)
- [Wat je nodig hebt](#wat-je-nodig-hebt)
- [Aan de slag](#aan-de-slag)
- [Zo werk je ermee](#zo-werk-je-ermee)
- [Sneltoetsen](#7-sneltoetsen)
- [Goed om te weten](#goed-om-te-weten)
- [Problemen oplossen](#problemen-oplossen)
- [Kosten (indicatie)](#kosten-indicatie)
- [Privacy & verantwoordelijkheid](#privacy--verantwoordelijkheid)
- [Techniek](#techniek)
- [Licentie](#licentie)

---

## Wat het doet

**Opnemen en transcriberen**

- **Opnemen** via de microfoon (met een keuzelijst als je er meerdere hebt), of
  **scherm + audio** delen voor online gesprekken — beide kanten van het gesprek worden
  dan opgenomen.
- **Bestand uploaden** in plaats van live opnemen. Naast audiobestanden kun je ook een
  videobestand kiezen; dat gaat ongewijzigd naar Mistral, dat er de spraak uit haalt.
- **Transcriptie** via Mistral **Voxtral**, met automatische **sprekerherkenning**
  (diarisatie): het transcript wordt gelabeld met "Spreker 1", "Spreker 2", …
- Het transcript is **bewerkbaar**: schaaf het bij voordat het verslag eruit geschreven
  wordt, of **plak een transcript** uit een ander programma en sla de opname over.

**Het verslag**

- Het verslag wordt geschreven door **Mistral Large 3** (`mistral-large-2512`), met een
  ingebouwde klinische systeemprompt die thematisch en feitelijk schrijft. Je hoeft niets in
  te stellen; wie wil, kan in de instellingen **Large 4 met nadenken** als proef kiezen.
- Een **behandelgesprek** krijgt geen secties voorgeschreven: het model kiest zelf de
  indeling die bij dít gesprek past. Een **intake** houdt de vaste kopjes, want daar is de
  volledigheid van de uitvraag juist wat je wilt afdwingen.
- Keuze tussen **intake-** en **behandelgesprek** (elk met een eigen opbouw), optioneel
  het geslacht van de cliënt, optionele **voorinformatie**, een **behandeldoel** (alleen
  voor de supervisie), **extra instructies**, een automatisch verzonnen **titel** en emoji
  bij kopjes.
- Het verslag verschijnt **al schrijvend** in beeld en staat zodra het klaar is
  **automatisch op je klembord**. Daarnaast staat hoe lang de opname duurde, voor je
  tijdregistratie.
- Een aparte controle zoekt **veiligheidssignalen** in het transcript (doodsgedachten,
  zelfbeschadiging, geweld, …) en zet ze boven het verslag, met de plek in het transcript.

**Bijsturen tot het klopt**

- **Zelf aanpassen**: het verslag is bewerkbaar zoals het er staat; kopiëren neemt je
  wijzigingen mee.
- **Waar staat dit?** Selecteer een zin in het verslag en zie waar die in het transcript
  staat — en of het transcript hem echt draagt.
- **Opnieuw genereren** met de instellingen zoals ze nu staan, uit hetzelfde transcript.
- **Verslag herzien**: je typt in gewone taal wat er anders moet, en het verslag wordt
  opnieuw geschreven met jouw aanwijzing erbij.
- **Versiegeschiedenis**: blader met ← en → tussen alle versies en zie bij elke versie
  welke aanwijzing hem opleverde.

**Overnemen in het dossier**

- Een **supervisie** in een apart venster: het onuitgesprokene, doelgerichtheid en de roos
  van Leary, met op verzoek **tips voor het volgende gesprek** — bedoeld voor jezelf, niet
  voor het dossier.
- Uit het verslag een **brief aan huisarts of verwijzer**, een **samenvatting voor de
  cliënt** in eenvoudige taal (B1) of **alleen het huiswerk**.
- **Kopiëren naar klembord** als platte tekst, Markdown of opgemaakte (HTML) tekst;
  het formaat mag je ook achteraf nog wisselen.
- Bij een intake krijgt **elke sectiekop een eigen kopieerknop**, die alleen de inhoud van
  die sectie kopieert — zonder de kopregel, voor een dossier met een apart veld per
  onderwerp.

**De bediening**

- **Sneltoetsen** voor alles wat je vaak doet: spatie start de opname (stoppen vraagt een
  tweede druk), `C` en `T` kopiëren, `?` toont het hele overzicht.
- Een **donkere modus** die je systeem volgt, met een knop om hem te wisselen.
- Een **golfbeeld en niveaumeters** tijdens de opname, zodat je ziet dát er geluid
  binnenkomt — met een waarschuwing als een bron tien seconden stil blijft.
- Een **rustige indeling**: de voortgang staat in de kopbalk, de instellingen zijn
  ingeklapt, en zodra er een verslag is schuift het transcript als naslag naar onderen.
- Je **keuzes blijven bewaard** tussen sessies (gesprekstype, taalmodel, uitvoerformaat,
  microfoon, vinkjes). Cliëntinhoud nadrukkelijk niet.
- Op een telefoon blijft het **scherm aan** tijdens de opname, zodat die niet stilvalt.

---

## Wat je nodig hebt

- **Een moderne browser.** Opnemen met de microfoon werkt in Chrome, Edge, Firefox en
  Safari (ook op iPhone en iPad): de app kiest zelf een opnameformaat dat de browser aankan.
  **"Scherm + audio"** werkt alleen in Chromium-browsers (Chrome, Edge, Brave, Vivaldi) —
  Firefox en Safari delen geen tabbladaudio. Uploaden van een bestaande opname werkt overal.
- **Een Mistral-account met betaalmethode**, en voor echte cliëntgegevens **ZDR aan**
  (zie [Stap 1](#stap-1--account-betaling-en-zero-data-retention)).
- **Een goede microfoon.** De kwaliteit van het verslag staat of valt met de kwaliteit
  van de opname. Een losse **vergadermicrofoon** (via USB of bluetooth verbonden) geeft
  duidelijk betere resultaten dan de **ingebouwde laptopmicrofoon**. Die laatste werkt
  wél, maar staat vaak verder weg en vangt meer omgevingsgeluid op, waardoor de
  transcriptie — en dus het verslag — minder nauwkeurig wordt. Zorg ook voor een rustige
  ruimte zonder achtergrondgeluid.

---

## Aan de slag

Geen zorgen als je niet technisch bent — hieronder staat het stap voor stap. Je hoeft
niets te installeren en geen code te begrijpen. Je doet dit één keer; daarna kun je de
app gewoon gebruiken.

### Inleiding — Wat is een API-sleutel, en waarom heb je die nodig?

Deze app heeft zelf geen "verstand": het werkelijke transcriberen en schrijven gebeurt
bij **Mistral**, een Europees AI-bedrijf. Om namens jou met Mistral te mogen praten, heeft
de app een soort persoonlijk toegangscode nodig: de **API-sleutel**.

Vergelijk het met een **bankpas met pincode voor je Mistral-account**: het is een lange,
geheime reeks tekens die bewijst "dit ben ik, en dit gebruik mag op mijn rekening worden
geboekt". Een paar dingen om te weten:

- De sleutel hoort **bij jouw Mistral-account**; het gebruik (en de kosten) gaan via jou.
- Houd hem **geheim**, net als een wachtwoord. Deel hem niet en zet hem niet online.
- Je kunt een sleutel altijd **verwijderen of vervangen** in je Mistral-account. Raakt
  hij zoek of gedeeld, dan maak je gewoon een nieuwe en gooi je de oude weg.
- In deze app blijft de sleutel **alleen in je eigen browser** staan (hij wordt nergens
  anders heen gestuurd dan naar Mistral). Op een gedeelde of openbare computer kun je hem
  beter na gebruik wissen met de knop **Wissen**.

### Stap 1 — Account, betaling en Zero Data Retention

1. Maak een account aan op **[console.mistral.ai](https://console.mistral.ai)**.
2. Voeg een **betaalmethode** toe. Het gebruik wordt per seconde audio en per stuk tekst
   afgerekend; voor losse gesprekken gaat het doorgaans om enkele centen (zie
   [Kosten](#kosten-indicatie)).
3. **Vraag Zero Data Retention (ZDR) aan.** Dit is de instelling waarmee Mistral je
   gegevens helemaal niet bewaart. Voor cliëntgesprekken beschouwen we dit als een
   **minimumvereiste** — niet als optie.
   - ZDR is beschikbaar op het **Scale-plan** en moet je **apart aanvragen** via het
     [Mistral Help Center](https://help.mistral.ai/en/articles/347612-can-i-activate-zero-data-retention-zdr)
     of de support; je geeft daarbij je reden op (verwerking van gezondheidsgegevens).
   - Na goedkeuring verschijnt ZDR in de **Privacy-instellingen** van je Admin Console.
     Controleer dáár dat het echt aan staat vóór je met echte cliëntgegevens werkt.
   - Krijg je ZDR (nog) niet? Lees dan eerst goed [PRIVACY.md](PRIVACY.md) en oefen met
     niet-herleidbare oefengesprekken.

### Stap 2 — Een API-sleutel aanmaken

1. Log in op [console.mistral.ai](https://console.mistral.ai).
2. Ga in het menu naar **API Keys** (rechtstreeks:
   [console.mistral.ai/api-keys](https://console.mistral.ai/api-keys)).
3. Klik op **Create new key** (of "Nieuwe sleutel"), geef hem eventueel een naam zoals
   "Sessienotitie" en bevestig.
4. Er verschijnt nu een lange tekenreeks. **Kopieer die meteen** — vaak kun je hem later
   niet meer volledig terugzien. Ben je hem kwijt, maak dan gewoon een nieuwe.

### Stap 3 — Open de app

Er zijn twee manieren. **Online** is voor dagelijks gebruik het handigst; **downloaden**
werkt volledig offline (op de verbinding met Mistral na). Bij beide gaan je audio en
transcript **rechtstreeks** van jouw browser naar Mistral — nooit langs de pagina of een
host.

**Aanbevolen — online via `https://`:**

Open **[klankschrift.github.io/sessienotitie](https://klankschrift.github.io/sessienotitie/)**
in je browser. Op dit vaste `https://`-adres onthoudt je browser je **microfoontoestemming**
en je **API-sleutel**, zodat je die maar één keer hoeft te geven en niet bij elke opname
opnieuw. Er wordt alleen het kale HTML-bestand geserveerd; alle aanvragen gaan rechtstreeks
naar Mistral.

> Maak er een **bladwijzer** van, dan open je de app voortaan met één klik.

**Alternatief — download het bestand (offline):**

Je hebt maar één bestand nodig: **`index.html`**. Je hoeft niets te installeren.

1. Open op de projectpagina het bestand **`index.html`** (klik op de bestandsnaam).
2. Klik rechtsboven het bestand op de knop **Download raw file** — het download-icoon
   (een pijltje omlaag). Gebruik niet "kopiëren" of "Raw bekijken".
3. Sla het op een vaste plek op, bijvoorbeeld je **bureaublad** of een map "Sessienotitie".
4. **Let op:** de bestandsnaam moet eindigen op **`.html`** (niet `.htm.txt` of `.txt`).
   Slaat je browser het toch als tekstbestand op, hernoem het dan zodat het op `.html`
   eindigt.

> Lukt het downloaden van het losse bestand niet? Klik dan op de groene knop **Code →
> Download ZIP**, pak het gedownloade ZIP-bestand uit (rechtsklik → "Alles uitpakken") en
> gebruik de `index.html` die erin zit.

**Openen:** dubbelklik op het gedownloade `index.html`. Het opent in je standaardbrowser en
werkt meteen. Je hebt geen internet nodig behalve voor de verbinding met Mistral zelf.

> **Let op bij de lokale versie:** omdat je een bestand op je eigen computer opent, onthoudt
> de browser je **microfoontoestemming niet** — die moet je bij elke keer opnemen opnieuw
> geven. Wil je dat niet, gebruik dan de online versie hierboven.

> Voor toegang tot de microfoon eist de browser een "veilige context": een lokaal geopend
> bestand voldoet daaraan, net als een `https://`-adres. Een gewone `http://`-host zonder
> slotje werkt niet voor opnemen.

### Stap 4 — Sleutel invoeren in de app

Plak je gekopieerde sleutel in het paneel **Mistral API-sleutel** en klik op **Opslaan**.
De app onthoudt hem in deze browser tot je op **Wissen** klikt. Je hoeft hem dus niet elke
keer opnieuw in te voeren (behalve in een privé/incognito-venster).

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

## Kosten (indicatie)

**De kosten vallen in de praktijk enorm mee.** Je betaalt rechtstreeks aan Mistral op basis
van gebruik — geen abonnement, geen minimum:

- **Verslag:** ongeveer **3 eurocent** per gesprek.
- **Transcriptie (Voxtral):** ongeveer **€0,003 per minuut** audio (Mistral rekent af in
  dollars, $0,003/min; in euro's komt dat vrijwel op hetzelfde neer). Een half uur kost dus
  zo'n **8 cent**, een vol uur ongeveer **16 cent**.
- **Herzien of opnieuw genereren:** kost telkens ongeveer een nieuw verslag (~3 cent). Het
  transcriberen gebeurt maar één keer, dus dat telt niet opnieuw mee.
- **Veiligheidscontrole:** ongeveer een cent, één keer per transcript. **Tips**, **Waar staat dit?** en de
  **documenten voor de cliënt** kosten alleen iets als je erom vraagt — een documentje uit
  het verslag een fractie van een cent.
- **Large 4 met nadenken** is duurder dan Large 3: het denkwerk telt mee.

Onder de streep blijft een doorsnee sessie meestal rond de **10 à 15 eurocent**; ook een vol
uur blijft ruim onder de 25 cent. Bewust koos deze app voor de **beste** modellen in plaats
van goedkopere: het kwaliteitsverschil is voor klinische verslagen veel meer waard dan de
paar cent die je ermee zou besparen.

Raadpleeg [mistral.ai/pricing](https://mistral.ai/pricing) voor actuele tarieven.

---

## Privacy & verantwoordelijkheid

Korte versie: audio en transcript gaan **rechtstreeks** van jouw browser naar het
Europese endpoint van Mistral (`api.eu.mistral.ai`). De maker van deze tool en een
eventuele host zien je gegevens niet. Mistral verwerkt
in de EU en is **ISO 27001-gecertificeerd** — een internationaal erkende beveiligingsnorm,
net als bij veel andere transcriptiediensten. Dat is een serieuze, geruststellende basis.
Zonder ZDR bewaart Mistral API-verkeer wel standaard ~30 dagen voor misbruikdetectie (niet
voor training).
**ZDR is daarom een minimumvereiste: gebruik dit voor cliëntgegevens pas als ZDR aanstaat.**
Ook mét ZDR voldoe je niet automatisch aan NEN 7510 — dat hangt af van je verdere
inrichting. Je blijft zelf verwerkingsverantwoordelijke en controleert elk verslag voordat
je het opneemt in het dossier.

Op je eigen computer blijft alleen je **API-sleutel** achter; opname, transcript, verslag
en versies verdwijnen zodra je de pagina sluit of ververst.

De volledige, realistische toelichting (dataretentie, Zero Data Retention, ISO 27001,
NEN 7510, AVG, eigen risico) staat in **[PRIVACY.md](PRIVACY.md)**.

> **Geen advies.** Deze documentatie is algemene uitleg, naar beste weten opgesteld, maar
> geen juridisch of professioneel advies en mogelijk onvolledig of verouderd. Controleer
> prijzen, voorwaarden en normen zelf bij de bron en raadpleeg bij twijfel je FG of een
> jurist. Gebruik van de software en vertrouwen op deze informatie zijn voor eigen risico;
> de makers aanvaarden geen aansprakelijkheid (zie [PRIVACY.md](PRIVACY.md) en
> [LICENSE](LICENSE)).

---

## Techniek

- Eén zelfstandig `index.html`-bestand: HTML, CSS en JavaScript inline. Geen build, geen
  dependencies, geen server.
- Opname met `MediaRecorder`. Het opnameformaat wordt gekozen uit wat de browser aankan
  (`audio/webm`, `audio/mp4`, `audio/ogg`) in plaats van vastgelegd — met `audio/webm` hard
  erin begint een opname op een iPhone niet eens. Tijdens de opname houdt een
  `WakeLock` het scherm aan. Bij schermdeling wordt de tabbladaudio uit `getDisplayMedia`
  via een `AudioContext` gemengd met de microfoon en het videospoor meteen gestopt.
- Spraakherkenning met sprekerherkenning:
  `POST https://api.eu.mistral.ai/v1/audio/transcriptions` (`voxtral-mini-latest`, met
  `diarize=true` en `timestamp_granularities=segment`). Opeenvolgende segmenten van
  dezelfde spreker worden samengevoegd tot "Spreker 1", "Spreker 2", …; herhalingsloops in
  het transcript worden eruit gefilterd.
- Verslag: `POST https://api.eu.mistral.ai/v1/chat/completions` (standaard
  `mistral-large-2512`, streaming via server-sent events). Supervisie, tips,
  veiligheidscontrole, **Waar staat dit?** en de documenten zijn losse, niet-gestreamde
  aanroepen op hetzelfde endpoint; alle behalve de documenten vragen om een JSON-antwoord.
  Met Large 4 met nadenken (`mistral-large-4`, `reasoning_effort: high`) komt het denkwerk
  als aparte stukken mee; de pagina toont alleen de tekst.
- Voor de veiligheidscontrole en **Waar staat dit?** gaat het transcript in genummerde
  fragmenten mee (elke regel, en een lange regel in stukken van een paar zinnen); het model
  noemt nummers, en de pagina markeert die stukken met de CSS Highlight-API zonder de tekst
  te veranderen.
- Het verslag is `contenteditable`; na elke wijziging wordt het teruggelezen naar Markdown,
  dat de bron blijft voor kopiëren, sectieknoppen en herzien.
- Alle status — transcript, verslag, supervisie, documenten en de versiegeschiedenis — leeft in het geheugen
  van de pagina. De enige uitzondering is de reservekopie van de opname in IndexedDB
  (`sessienotitie-vangnet`), die na een verslag, bij Nieuw gesprek of bij het sluiten van het
  tabblad wordt verwijderd (via een briefje in `localStorage` en een Web Lock per tabblad, zodat
  het ook lukt als de browser het opruimen tijdens het sluiten niet afmaakt). Naar `localStorage` gaan alleen de API-sleutel, de themakeuze en de
  instellingen (gesprekstype, taalmodel, uitvoerformaat, microfoon, opnamebron, vinkjes) — nooit
  cliëntinhoud.
- De Mistral API stuurt CORS-headers mee, waardoor de browser rechtstreeks mag aanroepen.

## Licentie

[MIT](LICENSE).
