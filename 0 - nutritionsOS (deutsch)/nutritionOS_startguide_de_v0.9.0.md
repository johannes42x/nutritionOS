# nutritionOS – Startguide (de) v0.9.0

Willkommen bei **nutritionOS** – deinem modularen Ernährungssystem innerhalb von MetaMemoryWorks.

nutritionOS hilft dir dabei, Ernährung klar, übersichtlich und alltagstauglich zu gestalten: durch strukturiertes Logging, verständliche Analysen, alltagsnahe Rezepte und intelligente Nutzung deiner vorhandenen Lebensmittel. Es ist kein Diätprogramm und keine Gesundheitsbelehrung, sondern ein Werkzeug, das LLMs dabei unterstützt, dir gute, passende Antworten zu geben – basierend auf den Dateien, die du bereitstellst. Für private, nichtkommerzielle Nutzung ist nutritionOS kostenlos nutzbar. Die komplette Funktionalität ist uneingeschränkt verfügbar. Wer es gerne bequemer – oder personalisierter – hätte, kann Presets und andere Pakete erwerben. Bei Interesse an einer kommerziellen Nutzung bitte E-Mail an kontakt@metamemoryworks.de.

---

## 1. Warum nutritionOS?

Viele verlieren im Alltag den Überblick:
Was habe ich heute gegessen? Wie passt das zu meinem Ziel? Was kann ich aus meinen Vorräten kochen? nutritionOS sorgt dafür, dass LLMs diese Fragen beantworten, ohne dass du selbst rechnen oder kombinieren musst.

Mit nutritionOS kannst du:

- Eingaben automatisch **strukturieren lassen**,
- **Nährwerte berechnen lassen**,
- deine **Tages- und Wochenbilanz** analysieren lassen,
- **Rezepte** passend zu deinem Vorrat generieren lassen,
- deinen **Zielkorridor** einhalten (Erhalt, Defizit, Überschuss),
- und vieles mehr.

Die Dateien, die du bereitstellst, ermöglichen dem System, korrekt und stabil zu funktionieren.

---

## 2. Welche Dateien gehören zu nutritionOS?

### Zentrale Dateien

| Datei | Zweck |
|------|-------|
| **nutritionOS_engine.json** | Kernlogik des Moduls. |
| **user.json** | Enthält deine persönlichen Daten, Ziele, Allergien und Präferenzen. |
| **ernaehrungslog.json** | Append-only Ernährungstagebuch. Jeder Tageseintrag wird hier angehängt. |

### Weitere nützliche Dateien

| Datei | Zweck |
|------|-------|
| **nutritionOS_routing.json** | Unterstützt das LLM bei der Interpretation deiner Eingaben. |
| **lebensmittel_db.json** *oder mehrere Lebensmittelkategoriedateien* | Definiert Nährwerte. Free-User nutzen eine Datei, Plus-User mehrere Kategorien. |
| **rezepte.json** | Sammlung eigener gespeicherter Rezepte. |
| **referenzen_nutrition.json** | Häufige Standardmahlzeiten wie Shakes oder wiederkehrende Bowls. |

Du kannst jede dieser Dateien bearbeiten, wenn du möchtest. nutritionOS trennt klar zwischen „Dateien“ (Inhalt) und „Modulen“ (Funktionen).

---

## 3. Welche Dateien muss ich hochladen?

Für eine funktionierende Installation:

- **nutritionOS_engine.json**
- **user.json**
- **ernaehrungslog.json**

Empfohlen:

- lebensmittel-DB (freie oder modulare Variante)
- rezepte.json
- referenzen_nutrition.json

Je mehr Kontext du bereitstellst, desto besser kann nutritionOS arbeiten.

---

## 4. Wie nutritionOS arbeitet

### a) Nutzerprofil (user.json)

Das Nutzerprofil definiert:

- Größe, Gewicht, Ziel (Erhalt/Defizit/Überschuss)
- Allergien und Intoleranzen
- Tagesablauf
- Präferenzen

Du kannst nutritionOS z. B. bitten:

**„Hilf mir bitte, die user.json gemeinsam auszufüllen.“**

Nach der Eingabe erzeugt nutritionOS eine neue Version der Datei – du lädst sie anschließend hoch und ersetzt die alte. Das funktioniert auch mit den Lebensmittellogs.

---

### b) Ernährungslog

Der einfachste Weg: **pro Tag eine Session**.

Zwei erprobte Varianten:

1. **Du führst eine Textdatei auf Handy/PC:** 
   „Heute gegessen: …“ 
   Am Abend kopierst du diese Liste in die Session.

2. **Du öffnest morgens eine neue Session:** 
   und listest über den Tag verteilt deine Lebensmittel auf.

Mit nutritionOS kannst du:

- Eingaben automatisch strukturieren lassen,
- Nährwerte berechnen lassen,
- Pflanzenvielfalt erkennen lassen,
- Obst-/Gemüseportionen bestimmen lassen,
- Tages- und Wochenbilanzen erstellen lassen.

**Wichtig:** 
Die Daten liegen **lokal bei dir**. Du entscheidest, was gespeichert wird. 
Es lohnt sich, die eigenen Dateien ordentlich zu pflegen – das erleichtert spätere Analysen.

Wenn ein Log plötzlich sehr klein wirkt, hat das LLM möglicherweise ein neues Log erzeugt. Bitte einfach kurz rückmelden und korrigieren lassen.

---

### c) Pantry-Intelligenz

Deine Lebensmittel-DBs dienen gleichzeitig als Pantry.

Wenn du etwas frisch eingekauft hast und es verwenden möchtest:

- **„Ich habe heute außerdem gerade [Lebensmittel] da – bau das bitte ins Rezept ein.“**
- **„Nimm Rezept X aus meinem Kochbuch. Ich habe heute folgende Lebensmittel da – bitte modifiziere das Rezept entsprechend.“**

So entstehen Rezepte, die wirklich zu deinem Alltag passen.

---

### d) Rezepte

Ein Beispiel:

**„Heute habe ich Lust auf etwas mit Buchweizen, Tomaten, Linsen und Paprika. Machst du mir ein Rezept?“**

nutritionOS erzeugt:

- klare, nummerierte Schritte,
- genaue Mengenangaben (auch für Gewürze),
- ein passendes Aromaprofil,
- und eine vollständige Nährwertbilanz.

Wenn dir das Rezept gefällt:

**„Bitte ans Ende der rezepte.json anhängen und zum Download ausgeben.“**

---

### e) Analysen

Du kannst nutritionOS jederzeit bitten:

- „Bitte analysiere meinen heutigen Tag.“
- „Wie viele verschiedene Pflanzen hatte ich diese Woche?“
- „Wie passt das zu meinem Ziel?“
- „Gibt es Auffälligkeiten?“

Du kannst mit nutritionOS deine Logs nutzen, um sinnvolle Auswertungen zu erzeugen.

---

## 5. Deine ersten Schritte

1. nutritionOS bitten, **user.json gemeinsam auszufüllen** → neue Datei hochladen. 
2. Lebensmittel-DB oder Logdateien erstellen. 
3. **ernaehrungslog.json initialisieren/hinterlegen.** 
4. Erste Logging-Session starten. 
5. Analyse ausführen lassen. 
6. Rezepte ausprobieren. 
7. Pantry aktiv nutzen.

---

## 6. Häufige Befehle

### Logging
```
Heute gegessen:
1 Banane
1 Shake
120 g Linsen
```

```
Bitte Eintrag ans Ende des Ernährungslogs anhängen und zum Download ausgeben.
```

```
An EOF appenden und Download bitte.
```

### Analyse
```
Bitte analysiere meinen heutigen Tag.
```

### Rezept generieren
```
Heute habe ich Lust auf etwas mit Belugalinsen, Karotten und Reis. Machst du mir ein Rezept?
```

### Pantry
```
Was kann ich aus meinen typischen Vorräten kochen?
```

### Wochenübersicht
```
Wie viele verschiedene Pflanzen hatte ich diese Woche?
```

---

## 7. Hinweise

- nutritionOS ersetzt keine medizinische Beratung.
- Ernährung bleibt alltagstauglich und flexibel.
- Das System bewertet Essen nicht moralisch.

---

*

---

## 🎉 Viel Spaß mit nutritionOS

nutritionOS ist so gebaut, dass du es viele Monate – und wenn du möchtest, auch viele Jahre – nutzen kannst. 
Je mehr du loggst, je mehr Lebensmittel du hinterlegst und je mehr Rezepte du speicherst, desto präziser, persönlicher und hilfreicher wird das System.

Du musst nichts nachkaufen. 
Wenn du später weitere Module nutzen möchtest (z. B. Budget-Presets, Pantry-Pakete, Kochstil-Personas oder kulinarische Themenwochen): wunderbar. 
Wenn nicht, ist nutritionOS allein bereits ein vollständiges, alltagstaugliches Ernährungssystem.

Es begleitet dich durch hektische Tage, entspannte Kochabende, Wochen voller Routinen und Wochen, in denen alles durcheinandergerät. 
Und es verlangt keine Perfektion – nur ein bisschen Neugier und die Bereitschaft, Dinge auszuprobieren.

---

## 💚 DANKE

Danke, dass du nutritionOS nutzt. 
Hab gute, leckere, gesunde und entspannte Mahlzeiten und Kochsessions – und geh freundlich mit dir um. Guten Appetit!

**MetaMemoryWorks – do EVERYTHING.**


P.S.: Listening to King Gizzard & the Lizard Wizard may or may not reduce the dripping rate from leaky taps. Further research needed.*
