# Sessienotitie

Een gespreksverslag-hulpmiddel voor psychologen en andere behandelaars, dat volledig in
de browser draait. Je neemt een gesprek op (of uploadt een audiobestand), waarna het
automatisch wordt **getranscribeerd** en omgezet in een gestructureerd, professioneel
**dossierverslag**. Alles verloopt via je **eigen Mistral API-sleutel** — er is geen
server en geen account bij de maker nodig.

Het hele programma is één bestand: `index.html`.

> 🧪 **Experimenteel project.** Dit is een vrij, open-source **experiment** — geen
> commercieel product, zonder ondersteuning, garanties of toezeggingen. Het wordt
> aangeboden zoals het is, zodat iedereen het kan bekijken, gebruiken en aanpassen. Of het
> voor jouw situatie geschikt en toelaatbaar is, beoordeel je zelf.

> ⚠️ **Lees eerst [PRIVACY.md](PRIVACY.md).** Dit is een hulpmiddel, geen kant-en-klare
> NEN 7510-conforme oplossing, en gebruik is voor eigen verantwoordelijkheid en risico.
>
> 🔒 **Minimumvereiste voor cliëntgegevens:** gebruik dit voor échte cliëntgesprekken
> **alleen als je bij Mistral _Zero Data Retention_ (ZDR) hebt aangevraagd en het aanstaat**.
> Zonder ZDR bewaart Mistral je gegevens standaard ongeveer 30 dagen — dat is voor
> gezondheidsgegevens niet acceptabel. Hoe je ZDR aanvraagt, staat bij
> [Stap 1](#stap-1--account-betaling-en-zero-data-retention).
>
> En zelfs **mét** ZDR ben je er niet automatisch: ZDR is *noodzakelijk maar niet
> voldoende* voor NEN 7510. Of je aan de norm voldoet, hangt ook af van hoe je de rest
> inricht (toegang, opslag, afspraken, toestemming). Zonder ZDR: gebruik de app alleen met
> niet-herleidbare oefengesprekken.

---

## Wat het doet

- **Opnemen** via de microfoon, of **scherm + audio** delen voor online gesprekken
  (beide kanten van het gesprek worden dan opgenomen).
- **Audiobestand uploaden** in plaats van live opnemen.
- **Transcriptie** via Mistral **Voxtral**, met automatische **sprekerherkenning**
  (diarisatie) die aangeeft wie wanneer spreekt, en het **verslag** via het beste Mistral-
  taalmodel (`mistral-large-latest`), met een ingebouwde klinische systeemprompt die
  thematisch en feitelijk schrijft. De app kiest deze modellen automatisch — je hoeft
  niets in te stellen.
- Keuze tussen **intake-** en **behandelgesprek**, optionele voorinformatie, extra
  instructies, automatische titel, emoji bij kopjes en losse "collegiale overwegingen".
- **Kopiëren naar klembord** als platte tekst, Markdown of opgemaakte (HTML) tekst.

---

## Aan de slag

Geen zorgen als je niet technisch bent — hieronder staat het stap voor stap. Je hoeft
niets te installeren en geen code te begrijpen. Je doet dit één keer; daarna kun je de
app gewoon gebruiken.

> 🎙️ **Belangrijk vooraf — gebruik een goede microfoon.** De kwaliteit van het verslag
> staat of valt met de kwaliteit van de opname. Een losse (USB- of dasspeld-)microfoon of
> een goede headset geeft duidelijk betere resultaten dan de **ingebouwde
> laptopmicrofoon**. Die laatste werkt wél, maar staat vaak verder weg en vangt meer
> omgevingsgeluid op, waardoor de transcriptie — en dus het verslag — minder nauwkeurig
> wordt. Zorg ook voor een rustige ruimte zonder achtergrondgeluid.

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
   niet meer volledig terugzien. Zie je hem kwijt te zijn, maak dan gewoon een nieuwe.

### Stap 3 — Download het bestand naar je computer

Je hebt maar één bestand nodig: **`index.html`**. Je hoeft niets te installeren.

**Downloaden van GitHub (de makkelijkste manier):**

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

> **Handig voor dagelijks gebruik:** sleep het geopende tabblad naar je bladwijzerbalk of
> maak een snelkoppeling op je bureaublad, zodat je het voortaan met één klik opent. Omdat
> je sleutel in de browser bewaard blijft, hoef je die niet opnieuw in te voeren.

**Voor gevorderden (optioneel):** je kunt `index.html` ook op een statische host zetten
(bijv. **GitHub Pages**) en via een `https://`-adres openen. Ook dan gaan je audio en
transcript nooit langs die host — alleen het kale HTML-bestand wordt geserveerd; de
aanvragen gaan rechtstreeks van jouw browser naar Mistral.

> Voor toegang tot de microfoon eist de browser een "veilige context": een lokaal geopend
> bestand voldoet daaraan, net als een `https://`-adres. Een gewone `http://`-host zonder
> slotje werkt niet voor opnemen.

### Stap 4 — Sleutel invoeren in de app

Plak je gekopieerde sleutel in het paneel **Mistral API-sleutel** en klik op **Opslaan**.
De app onthoudt hem in deze browser tot je op **Wissen** klikt. Je hoeft hem dus niet elke
keer opnieuw in te voeren (behalve in een privé/incognito-venster).

### Stap 5 — Gebruiken

1. Kies het **type gesprek** (intake of behandel) en eventueel het geslacht van de cliënt.
2. Klik op de ronde knop om op te nemen — of upload een bestaand audiobestand.
3. Klik nogmaals om te stoppen. Transcriptie en verslag verschijnen automatisch.
4. **Controleer het verslag** en klik op **Kopiëren naar klembord**; plak het in het dossier.

---

## Kosten (indicatie)

**De kosten vallen in de praktijk enorm mee.** Je betaalt rechtstreeks aan Mistral op basis
van gebruik — geen abonnement, geen minimum:

- **Verslag:** ongeveer **3 eurocent** per gesprek.
- **Transcriptie (Voxtral):** ongeveer **€0,003 per minuut** audio (Mistral rekent af in
  dollars, $0,003/min; in euro's komt dat vrijwel op hetzelfde neer). Een half uur kost dus
  zo'n **8 cent**, een vol uur ongeveer **16 cent**.

Onder de streep blijft een doorsnee sessie meestal rond de **10 à 15 eurocent**; ook een vol
uur blijft ruim onder de 25 cent. Bewust koos deze app voor de **beste** modellen in plaats
van goedkopere: het kwaliteitsverschil is voor klinische verslagen veel meer waard dan de
paar cent die je ermee zou besparen.

Raadpleeg [mistral.ai/pricing](https://mistral.ai/pricing) voor actuele tarieven.

---

## Privacy & verantwoordelijkheid

Korte versie: audio en transcript gaan **rechtstreeks** van jouw browser naar Mistral
(EU). De maker van deze tool en een eventuele host zien je gegevens niet. Mistral verwerkt
in de EU en is **ISO 27001-gecertificeerd** — een internationaal erkende beveiligingsnorm,
net als bij veel andere transcriptiediensten. Dat is een serieuze, geruststellende basis.
Zonder ZDR bewaart Mistral API-verkeer wel standaard ~30 dagen voor misbruikdetectie (niet
voor training).
**ZDR is daarom een minimumvereiste: gebruik dit voor cliëntgegevens pas als ZDR aanstaat.**
Ook mét ZDR voldoe je niet automatisch aan NEN 7510 — dat hangt af van je verdere
inrichting. Je blijft zelf verwerkingsverantwoordelijke en controleert elk verslag voordat
je het opneemt in het dossier.

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
- Spraakherkenning met sprekerherkenning (diarisatie): `POST https://api.mistral.ai/v1/audio/transcriptions` (`voxtral-mini-latest`, met `diarize`). Het transcript wordt per spreker gelabeld ("Spreker 1", "Spreker 2", …).
- Verslag: `POST https://api.mistral.ai/v1/chat/completions` (streaming).
- De Mistral API stuurt CORS-headers mee, waardoor de browser rechtstreeks mag aanroepen.

## Licentie

[MIT](LICENSE).
