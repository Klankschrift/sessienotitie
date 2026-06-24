# Privacy, verantwoordelijkheid en NEN 7510

Deze tool verwerkt **bijzondere persoonsgegevens** (gezondheidsgegevens). Lees deze
toelichting voordat je hem in de praktijk gebruikt. De tekst is bewust eerlijk: niet
alarmerend, maar ook niet mooier dan het is.

## In het kort

- Audio en transcript gaan **rechtstreeks van jouw browser naar Mistral**. Er zit geen
  tussenserver van de maker tussen; de maker en een eventuele host zien je gegevens niet.
- Je **API-sleutel** blijft lokaal in je browser (`localStorage`) en wordt alleen
  meegestuurd naar Mistral.
- Mistral verwerkt in de **EU** en is **ISO 27001**-gecertificeerd.
- **Minimumvereiste: gebruik dit voor échte cliëntgegevens alleen als je _Zero Data
  Retention_ (ZDR) bij Mistral hebt aangevraagd en aanstaat.** Zonder ZDR bewaart Mistral
  je gegevens standaard ~30 dagen. Zie [hieronder](#zero-data-retention-zdr--minimumvereiste).
- ZDR is **noodzakelijk maar niet voldoende** voor NEN 7510: ook met ZDR hangt het af van
  hoe je de rest inricht.
- Dit is een **hulpmiddel**, geen kant-en-klare NEN 7510-conforme oplossing. Je blijft
  zelf verwerkingsverantwoordelijke.
- Gebruik is **voor eigen risico en verantwoordelijkheid**.

## Hoe de gegevens stromen

Alles draait in je eigen browser. Wanneer je opneemt of een bestand uploadt:

1. De audio wordt rechtstreeks naar de transcriptie-API van Mistral gestuurd.
2. Het transcript komt terug en wordt — opnieuw rechtstreeks — naar het tekstmodel van
   Mistral gestuurd om het verslag te genereren.

Er is geen backend van deze applicatie. Ook als je `index.html` via een statische host
(zoals GitHub Pages) opent, wordt alleen het kale HTML-bestand geserveerd; je audio,
transcript en verslag passeren die host niet.

## Mistral: dataretentie en training

Op basis van de informatie van Mistral (controleer altijd de actuele
[privacyvoorwaarden](https://legal.mistral.ai/terms/privacy-policy)):

- **Retentie:** standaard bewaart Mistral API-invoer en -uitvoer ongeveer **30 dagen** om
  misbruik te detecteren, waarna het wordt verwijderd.
- **Training:** API-gegevens worden **niet** gebruikt om modellen te trainen, tenzij je
  daar expliciet voor kiest (opt-in).
- **Locatie:** verwerking vindt plaats in de **EU** (Frankrijk).
- **Certificering:** Mistral is **ISO 27001**-gecertificeerd, de internationaal erkende
  norm voor informatiebeveiliging. Dat is een serieuze waarborg en een goede basis — net
  als bij veel andere transcriptie- en AI-diensten die in de zorg worden gebruikt.

### Zero Data Retention (ZDR) — minimumvereiste

ZDR betekent dat Mistral helemaal niets bewaart na het beantwoorden van een verzoek (ook
het venster van 30 dagen vervalt dan). **Voor het verwerken van cliëntgesprekken is dit een
minimumvereiste, geen optie: zet ZDR aan voordat je echte gegevens verwerkt.** Met ZDR sluit
je het belangrijkste privacyrisico van een clouddienst — bewaring van gevoelige gegevens —
zo goed mogelijk uit.

Wees je bewust van de praktische kant, want **ZDR is niet standaard actief**:

- Het is beschikbaar op het **Scale-plan** en alleen voor stateless API-aanvragen (zoals
  deze app gebruikt).
- Je moet het **apart aanvragen en laten goedkeuren** via het
  [Mistral Help Center](https://help.mistral.ai/en/articles/347612-can-i-activate-zero-data-retention-zdr)
  of de support, met opgave van je reden (verwerking van gezondheidsgegevens is een
  legitieme reden).
- Na goedkeuring zie je ZDR terug in de **Privacy-instellingen** van je Admin Console.
  **Controleer daar dat het echt aanstaat** voordat je met cliëntgegevens werkt.

Krijg of wil je geen ZDR? Gebruik de app dan niet voor herleidbare cliëntgegevens, maar
bijvoorbeeld voor oefengesprekken — of overweeg **lokale transcriptie** (zoals een lokaal
draaiend Whisper-model) zodat audio je computer niet verlaat.

## NEN 7510 en de AVG

NEN 7510 is de Nederlandse norm voor informatiebeveiliging in de zorg. Deze tool maakt
gebruik van een ISO 27001-gecertificeerde dienst (Mistral), wat een goede basis is, maar:

> **Een tool kan niet "NEN 7510-conform" zijn; een organisatie is dat (of niet).**

Met andere woorden: ZDR (zie hierboven) is **noodzakelijk maar niet voldoende**. Het is de
ondergrens, maar of je daadwerkelijk aan NEN 7510 voldoet, hangt af van hoe je het geheel
inricht. NEN 7510 gaat over je hele werkwijze: beleid, afspraken, toegang, bewustzijn en
risico's. Als behandelaar of praktijk blijf je **verwerkingsverantwoordelijke** in de zin
van de AVG. Dat betekent concreet dat je zelf:

- een **verwerkersovereenkomst** met Mistral beoordeelt en aangaat (zie hun
  [Data Processing Addendum](https://legal.mistral.ai/terms/data-processing-addendum));
- afweegt of cloudtranscriptie van gespreksopnamen past binnen je
  informatiebeveiligings- en privacybeleid;
- cliënten **informeert** over deze verwerking en waar nodig **toestemming** vraagt;
- **ZDR aanzet** (de minimumvereiste, zie hierboven), of — als dat niet kan — kiest voor
  **lokale transcriptie** (bijvoorbeeld een lokaal Whisper-model) zodat audio je computer
  niet verlaat;
- de gangbare voorzorgen treft: opnamen en verslagen veilig opslaan, niet langer bewaren
  dan nodig, en de API-sleutel beschermen.

Dit is geen juridisch advies. Twijfel je of deze werkwijze binnen jouw kaders past, leg
het dan voor aan de functionaris gegevensbescherming (FG) of privacyjurist van je
organisatie.

## Geen advies — informatie kan onjuist of verouderd zijn

Dit document en het README zijn bedoeld als **algemene uitleg, niet als juridisch,
medisch of professioneel advies**. Ze zijn naar beste weten opgesteld op het moment van
schrijven, maar:

- De makers geven **geen garantie** dat de informatie juist, volledig of actueel is.
- Gegevens over Mistral (prijzen, dataretentie, ZDR, certificeringen, voorwaarden) en over
  regelgeving (NEN 7510, AVG) **kunnen wijzigen** en kunnen per situatie anders uitpakken.
  **Controleer alles zelf** bij de bron: de actuele
  [voorwaarden](https://legal.mistral.ai/terms/privacy-policy) en
  [prijzen](https://mistral.ai/pricing) van Mistral, en de geldende normen.
- Of jouw werkwijze voldoet aan NEN 7510 en de AVG is een afweging die **jij** maakt, zo
  nodig met je **functionaris gegevensbescherming (FG), een privacyjurist of je
  beroepsvereniging**. Vertrouw daarvoor niet uitsluitend op dit document.
- Beslissingen die je op basis van deze informatie neemt, zijn **voor eigen
  verantwoordelijkheid en risico**.

## Eigen risico en aansprakelijkheid

Deze software wordt geleverd "as is", zonder enige garantie (zie de
[MIT-licentie](LICENSE)). Gebruik is volledig voor eigen verantwoordelijkheid en risico.
In het bijzonder:

- **Transcriptie en taalmodellen maken fouten.** Een verslag kan onjuistheden,
  weglatingen of verzonnen details bevatten. **Controleer en corrigeer elk verslag
  voordat je het opneemt in het dossier.** De inhoudelijke verantwoordelijkheid voor het
  dossier ligt volledig bij jou als behandelaar.
- De makers en verspreiders van deze tool aanvaarden, voor zover wettelijk toegestaan,
  **geen enkele aansprakelijkheid** voor schade, gegevensverlies, datalekken,
  onjuistheden of gevolgen van keuzes die voortvloeien uit het gebruik van de software of
  uit het vertrouwen op deze documentatie.
- Mistral is een externe dienst met eigen voorwaarden; controleer die zelf en houd
  rekening met wijzigingen.

> Een disclaimer beperkt aansprakelijkheid, maar sluit die naar Nederlands recht nooit
> volledig uit (bijvoorbeeld bij opzet of bewuste roekeloosheid). Wil je als verspreider
> zoveel mogelijk zekerheid, laat de tekst dan eenmalig nakijken door een jurist.
