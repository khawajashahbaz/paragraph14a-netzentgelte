# § 14a EnWG Netzentgelte – Preisblätter deutscher Netzbetreiber

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23806543.svg)](https://doi.org/10.5281/zenodo.23806543)

**Stand: 27.10.2026** · Lizenz: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.de) · Herausgeber: [Kilowattheim](https://kilowattheim.com/de), Muhammad Shahbaz ([ORCID](https://orcid.org/0009-0002-8164-8353))

Wer eine Wärmepumpe, Wallbox, Klimaanlage oder einen Stromspeicher mit mehr als 4,2 kW nach § 14a EnWG steuern lässt, zahlt weniger Netzentgelt. Wie viel weniger, legt jeder Netzbetreiber in seinem Preisblatt fest. Dieser Datensatz sammelt die Preise von 17 Netzbetreibern für 2026 und 2027 in einer Tabelle und rechnet sie für einen Beispielhaushalt durch.

Die Daten sind dieselben wie im Vergleich auf **[kilowattheim.com/de/netzentgelt-14a/vergleich](https://kilowattheim.com/de/netzentgelt-14a/vergleich)**. Dort gibt es auch einen Rechner für den eigenen Verbrauch.

*English summary below.*

## Dateien

| Datei | Inhalt |
|---|---|
| [`data/netzentgelte-14a.csv`](data/netzentgelte-14a.csv) | Eine Zeile je Preisblatt (Netzbetreiber und Jahr). UTF-8, Komma als Trennzeichen, Punkt als Dezimalzeichen. |
| [`data/netzentgelte-14a.json`](data/netzentgelte-14a.json) | Dieselben Zeilen unter `preisblaetter`, dazu Stand, Lizenz, Beispielhaushalt und Einheiten. |

## Was die Daten zeigen

Preise für Haushaltskunden im Niederspannungsnetz ohne Leistungsmessung, so wie sie im Preisblatt stehen: **netto**, ohne Umsatzsteuer, Konzessionsabgabe, Umlagen und Messstellenbetrieb.

- **Modul 1:** pauschale Ermäßigung pro Jahr (im Preisblatt meist als negativer Betrag; hier als positive Ermäßigung).
- **Modul 2:** reduzierter Arbeitspreis für ein Gerät mit eigenem Zähler, statt Modul 1.
- **Modul 3:** zeitvariabler Arbeitspreis (Standard-, Hoch- und Niedrigtarif), nur zusammen mit Modul 1.

Die Spalten `beispiel_*` rechnen jedes Preisblatt für einen **Beispielhaushalt** durch: 2.500 kWh Haushaltsstrom plus 4.000 kWh für Wärmepumpe oder Wallbox im Jahr, Netzentgelt aus Grund- und Arbeitspreis, **brutto mit 19 % Umsatzsteuer**, pro Jahr. Bei Modul 1 + 3 ist der Verbrauch des Geräts gleichmäßig über Tag und Jahr verteilt; wer gezielt im Niedrigtarif heizt oder lädt, spart mehr. Die Kosten eines zweiten Zählers für Modul 2 sind nicht eingerechnet. Die Website rundet diese Beträge auf ganze Euro, die Dateien enthalten die Cent.

### Spalten

| Spalte | Bedeutung |
|---|---|
| `netzbetreiber_id`, `netzbetreiber` | Kurzname und Firmenname |
| `jahr`, `gueltig_ab`, `gueltig_bis` | Gültigkeit des Preisblatts |
| `status` | `final` = endgültig, `vorlaeufig` = vorläufiges Preisblatt (die endgültigen erscheinen meist Mitte Dezember) |
| `grundpreis_eur_a` | Grundpreis, € pro Jahr, netto |
| `arbeitspreis_ct_kwh` | Arbeitspreis, ct/kWh, netto |
| `modul1_ermaessigung_eur_a` | Ermäßigung Modul 1, € pro Jahr, netto |
| `modul2_ct_kwh` | Arbeitspreis Modul 2, ct/kWh, netto |
| `modul3_st_ct_kwh`, `modul3_ht_ct_kwh`, `modul3_nt_ct_kwh` | Modul 3: Standard-, Hoch- und Niedrigtarif, ct/kWh, netto |
| `modul3_ht_zeiten`, `modul3_nt_zeiten` | Uhrzeiten von Hoch- und Niedrigtarif |
| `modul3_gilt` | Zeitraum, in dem Modul 3 gilt (leer: im Preisblatt nicht angegeben) |
| `beispiel_ohne_14a_eur` … `beispiel_modul1_modul3_eur` | Netzentgelt des Beispielhaushalts, € pro Jahr, brutto |
| `beispiel_beste_variante`, `beispiel_ersparnis_eur` | günstigste Variante und ihre Ersparnis gegenüber „ohne § 14a“, € pro Jahr, brutto |
| `quelle_titel`, `quelle_url` | das Preisblatt des Netzbetreibers |
| `verified_at` | Datum, an dem wir die Zeile gegen das Preisblatt geprüft haben |
| `kilowattheim_url` | Seite des Netzbetreibers auf Kilowattheim, mit allen Preisen und Rechner |

### Netzbetreiber

| Netzbetreiber | 2026 | 2027 |
|---|---|---|
| [badenovaNETZE GmbH](https://kilowattheim.com/de/netzentgelt-14a/badenova-netze) | endgültig | vorläufig |
| [Bayernwerk Netz GmbH](https://kilowattheim.com/de/netzentgelt-14a/bayernwerk-netz) | endgültig | vorläufig |
| [Braunschweiger Netz GmbH](https://kilowattheim.com/de/netzentgelt-14a/bs-netz) | endgültig | vorläufig |
| [Dortmunder Netz GmbH (DONETZ)](https://kilowattheim.com/de/netzentgelt-14a/donetz) | endgültig | vorläufig |
| [enercity Netz GmbH](https://kilowattheim.com/de/netzentgelt-14a/enercity-netz) | endgültig | vorläufig |
| [Hamburger Energienetze GmbH](https://kilowattheim.com/de/netzentgelt-14a/hamburger-energienetze) | endgültig | vorläufig |
| [MVV Netze GmbH](https://kilowattheim.com/de/netzentgelt-14a/mvv-netze) | endgültig | vorläufig |
| [Netz Leipzig GmbH](https://kilowattheim.com/de/netzentgelt-14a/netz-leipzig) | endgültig | noch nicht veröffentlicht |
| [Netze BW GmbH](https://kilowattheim.com/de/netzentgelt-14a/netze-bw) | endgültig | vorläufig |
| [Netze Duisburg GmbH](https://kilowattheim.com/de/netzentgelt-14a/netze-duisburg) | endgültig | vorläufig |
| [Netzgesellschaft Düsseldorf mbH](https://kilowattheim.com/de/netzentgelt-14a/netz-duesseldorf) | endgültig | vorläufig |
| [Netzgesellschaft Potsdam GmbH](https://kilowattheim.com/de/netzentgelt-14a/ngp-potsdam) | endgültig | vorläufig |
| [RheinNetz GmbH](https://kilowattheim.com/de/netzentgelt-14a/rheinnetz) | endgültig | vorläufig |
| [Stromnetz Berlin GmbH](https://kilowattheim.com/de/netzentgelt-14a/stromnetz-berlin) | endgültig | vorläufig |
| [Stuttgart Netze GmbH](https://kilowattheim.com/de/netzentgelt-14a/stuttgart-netze) | endgültig | vorläufig |
| [SWM Infrastruktur GmbH & Co. KG](https://kilowattheim.com/de/netzentgelt-14a/swm-infrastruktur) | endgültig | vorläufig |
| [Westnetz GmbH](https://kilowattheim.com/de/netzentgelt-14a/westnetz) | endgültig | vorläufig |

## Quellen

- **Preise:** die veröffentlichten Preisblätter der Netzbetreiber, je Zeile verlinkt in `quelle_url`. Stuttgart Netze sperrt automatische Downloads; dort verweist `quelle_url` auf die Seite mit den Veröffentlichungen. Die Preistabellen der Netzgesellschaft Potsdam sind als Grafik gedruckt und wurden von der gerenderten PDF-Seite abgelesen.
- **Regeln für die Module:** [BNetzA, Festlegung BK8-22/010-A (NSAVER) vom 23.11.2023](https://www.bundesnetzagentur.de/DE/Beschlusskammern/1_GZ/BK8-GZ/2022/2022_4-Steller/BK8-22-0010/BK8-22-0010-A_Festlegung_DL_BF.pdf?__blob=publicationFile&v=6). Jedes Preisblatt prüfen wir gegen die Formel für Modul 1, den Anteil für Modul 2 und die Spannen für Modul 3.
- **Methodik:** [kilowattheim.com/de/methodik](https://kilowattheim.com/de/methodik)

Hinweis zu badenovaNETZE: Laut Preisblatt enthalten die Preise Netznutzung und Messstellenbetrieb, die Messentgelte stehen aber auf einer eigenen Seite. Der Grundpreis ist so übernommen, wie er gedruckt ist.

Die Daten sind sorgfältig geprüft, aber ohne Gewähr. Maßgeblich ist das Preisblatt Ihres Netzbetreibers. Keine Rechts- oder Energieberatung.

## Lizenz und Quellenangabe

Die Tabellen stehen unter der Lizenz **[Creative Commons Namensnennung 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/deed.de)**, Volltext in [`LICENSE`](LICENSE). Sie dürfen sie kopieren, weiterverarbeiten und veröffentlichen, auch kommerziell und in Artikeln, wenn Sie Kilowattheim als Quelle nennen und auf die Seite verlinken. Die Preise selbst stammen aus den Preisblättern der Netzbetreiber.

**Quellenangabe zum Kopieren:**

Text:

```
Daten: Kilowattheim, „§ 14a Netzentgelte im Vergleich“, Stand 27.10.2026, https://kilowattheim.com/de/netzentgelt-14a/vergleich, Lizenz: CC BY 4.0
```

HTML (für Websites):

```html
Daten: <a href="https://kilowattheim.com/de/netzentgelt-14a/vergleich">Kilowattheim – § 14a Netzentgelte im Vergleich</a>, Stand 27.10.2026, Lizenz: <a href="https://creativecommons.org/licenses/by/4.0/deed.de">CC BY 4.0</a>
```

Markdown:

```markdown
Daten: [Kilowattheim – § 14a Netzentgelte im Vergleich](https://kilowattheim.com/de/netzentgelt-14a/vergleich), Stand 27.10.2026, Lizenz: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.de)
```

Wenn Sie nur einen Netzbetreiber zitieren, verlinken Sie gern dessen Seite aus der Spalte `kilowattheim_url`.

Für wissenschaftliche Arbeiten: Zitierangaben stehen in [`CITATION.cff`](CITATION.cff). Jede Version ist bei Zenodo archiviert; die DOI [10.5281/zenodo.23806543](https://doi.org/10.5281/zenodo.23806543) führt immer zur neuesten Version.

```
Shahbaz, Muhammad; Kilowattheim (2026): § 14a EnWG Netzentgelte – Preisblätter deutscher Netzbetreiber, Stand 27.10.2026. Zenodo. https://doi.org/10.5281/zenodo.23806543
```

## Aktualisierung

Wir prüfen jede Zeile spätestens alle fünf Wochen gegen das Preisblatt. Die endgültigen Preisblätter für 2027 erscheinen meist Mitte Dezember 2026; dann ersetzen wir die vorläufigen Zeilen und veröffentlichen eine neue Version. Aktuell ist immer die Seite auf [kilowattheim.com](https://kilowattheim.com/de/netzentgelt-14a/vergleich).

Fehler gefunden? Bitte ein Issue in diesem Repository öffnen, am besten mit Link zum Preisblatt.

---

## English summary

**§ 14a EnWG grid fees of German distribution system operators, as of 27 October 2026.** Under § 14a of the German Energy Industry Act, households whose heat pump, wallbox, air conditioner or battery (> 4.2 kW) can be controlled by the grid operator pay reduced grid fees. Each operator publishes its own prices. This dataset collects the 2026 and 2027 price sheets of 17 operators: base price, energy price and the three § 14a modules (Modul 1: flat annual reduction; Modul 2: reduced energy price for a separately metered device; Modul 3: time-of-use energy price, combined with Modul 1). Prices are **net** of VAT, as printed. 2027 sheets are mostly preliminary (`vorlaeufig`); final ones are usually published in mid-December. The `beispiel_*` columns give the yearly grid fee, **including 19 % VAT**, for an example household using 2,500 kWh plus 4,000 kWh for the device.

Sources: each operator's price sheet (`quelle_url`) and BNetzA ruling BK8-22/010-A. Licence: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Attribution:

```html
Data: <a href="https://kilowattheim.com/de/netzentgelt-14a/vergleich">Kilowattheim – § 14a Netzentgelte im Vergleich</a>, as of 27 Oct 2026, licence: <a href="https://creativecommons.org/licenses/by/4.0/">CC BY 4.0</a>
```
