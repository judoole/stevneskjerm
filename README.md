# Stevneskjerm

Delt skjerm for judostevner: kamplista fra Smoothcomp på den ene halvdelen, infosider med tekst og bilder på den andre.

Skjermen henter innholdet på nytt hvert minutt. Når du endrer noe her i repoet, vises det på TV-en etter et par minutter, uten at noen trenger å røre maskinen som står koblet til.

## Endre tekst og innstillinger

Alt styres av [`stevne.md`](stevne.md). Åpne filen, trykk på blyanten, gjør endringene og trykk **Commit changes**. Det går fint fra mobilen også.

Øverst i filen, mellom de to `---`-linjene, står innstillingene:

| Innstilling | Hva den gjør |
|---|---|
| `smoothcomp` | Lenken til kamplista i TV-modus |
| `kamplista` | `venstre` eller `høyre` |
| `bredde` | Hvor stor del av skjermen kamplista får, i prosent |
| `zoom` | Tekststørrelse i kamplista, i prosent |
| `sekunder` | Hvor lenge hver infoside vises |
| `qr` | `auto`, `nei` eller en egen lenke |
| `oppfrisk` | Last kamplista på nytt hvert X minutt (0 = aldri) |

Under innstillingene kommer infosidene. En linje som bare inneholder `---` starter en ny side.

```markdown
# Kiosken er åpen

Kaffe, vafler og saft.
Betal med Vipps.

---

# Program

| Tid | |
|---|---|
| 09.00 | Innveiing |
| 10.00 | Første kamp |

---

![](bilder/sponsorer.jpg)
```

- `#` gir stor overskrift, `##` mindre overskrift, `-` gir punktliste.
- Linjeskift i teksten blir linjeskift på skjermen.
- Blir det mye tekst på en side, krymper skriften til den får plass.
- En side med bare et bilde fyller hele infohalvdelen.

## Legge til bilder

1. Gå til mappen [`bilder`](bilder).
2. Trykk **Add file** og **Upload files**, og velg bildet.
3. Bruk bildet i `stevne.md` slik: `![](bilder/navnet-på-bildet.jpg)`

Bilder som skal fylle hele infohalvdelen, passer best i omtrent 960 × 840 piksler.

Skal du bytte ut et bilde, gi det nye bildet et nytt navn. Ellers kan skjermen vise det gamle bildet i opptil ti minutter.

## På stevnedagen

1. Koble en PC til TV-en med HDMI.
2. Åpne skjermen i Chrome: `https://<brukernavn>.github.io/stevneskjerm/`
3. Trykk **F** for fullskjerm.

| Tast | |
|---|---|
| F | Fullskjerm av og på |
| ← → | Forrige og neste infoside |
| + − | Større og mindre kampliste, til siden lastes på nytt |
| R | Hent innholdet og last kamplista på nytt |
| H | Hjelp, med lenke hit og tidspunkt for siste henting |

Tastene virker ikke etter at du har klikket inne i kamplista. Klikk på infosiden først.

Er kamplista tom og det står at siden nektet tilkobling, slipper ikke Smoothcomp kamplista inn i siden. Trykk **H** og **Åpne kamplista i eget vindu**, og legg vinduene side om side.

## Teste lokalt

Siden må hente `stevne.md`, så den virker ikke når `index.html` åpnes rett som en fil. Start en enkel webserver i mappen:

```sh
python3 -m http.server 8000
```

Åpne så `http://localhost:8000`.
