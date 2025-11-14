# ZK/RK Generator v7.1

**Tool zur Analyse von Zielkonflikten (ZK) in gesellschaftlichen Transformationsprozessen**

🔗 **Live Demo:** https://burmeister12439-futur2.github.io/zk-generator/

---

## 🎯 Was ist das?

Dieses Tool hilft bei der systematischen Analyse von **Zielkonflikten (ZK)** in Transformationsprozessen. Es kombiniert:

- ✅ **Pattern-Matching** für strukturierte Texte
- 🤖 **KI-gestützte Analyse** (Claude API) für komplexe ethische/politische Debatten
- 🔄 **Refinement-System** zum Präzisieren der Pole
- 💾 **Lokale Speicherung** aller analysierten ZKs
- 📥 **CSV-Export** für weitere Analyse

---

## 🚀 Schnellstart

1. **Öffne:** https://burmeister12439-futur2.github.io/zk-generator/
2. **Text einfügen** (z.B. Policy-Dokument, Zeitungsartikel)
3. **"Analysieren" klicken**
4. **Ergebnis prüfen** und ggf. mit 🔄-Buttons verfeinern
5. **Speichern** für spätere Analyse

---

## 📖 Anwendungsbeispiele

### **Beispiel 1: Förder-Text (Pattern-Matching)**

**Text:**
```
Ohne Förderung kein Fortschritt: Kommunen warten auf neues 
Innenstadtprogramm. Viele Kommunen haben Konzepte entwickelt, 
können diese aber ohne finanzielle Unterstützung nicht umsetzen.
```

**Ergebnis:**
- ✅ Pol A: Förderung
- ✅ Pol B: Fortschritt
- ⏱️ Zeit: <1 Sekunde (Pattern erkannt)

---

### **Beispiel 2: Ethik-Debatte (KI-Analyse)**

**Text:**
```
Sollen sehr alte Patienten noch teure Behandlungen erhalten? 
Der Drogenbeauftragte ist skeptisch. Patientenschützer und 
die Linke sind empört.
```

**Workflow:**
1. Pattern scheitert → "🤖 KI-Analyse starten" erscheint
2. Klick → KI analysiert (2-3 Sek)
3. **Ergebnis:** Ressourceneffizienz ↔ Therapieanspruch
4. Optional: 🔄 verfeinern zu "Kostenorientierte Medizinethik ↔ Unbedingter Lebensschutz"

---

## 🛠️ Features im Detail

### **1. Intelligente Pol-Extraktion**

**3-Stufen-Ansatz:**

```
Stufe 1: Pattern-Matching (schnell, ~0.001s)
         ↓ Erfolg? → Zeige Vorschlag
         ↓ Scheitert?

Stufe 2: Qualitätsprüfung
         ↓ Pattern-Ergebnis zu schlecht?

Stufe 3: KI-Fallback (Claude API, ~2-3s)
         → User entscheidet: KI oder Manuell
```

---

### **2. Refinement-System**

Nach Auto-Vorschlag (Pattern oder KI):
- **🔄-Buttons** erscheinen neben Pol A und B
- Klick → Dialog mit 4-5 Alternativen
- Wählen → Automatisch neu analysieren

**Beispiel-Alternativen:**
- "Förderung" → "Finanzierung Innenstadtprogramme"
- "Ressourceneffizienz" → "Kostenorientierte Medizinethik"
- "Therapieanspruch" → "Unbedingter Lebensschutz"

---

### **3. ZK-Bewertung**

**Qualitäts-Checks (Q):**
- ✓ Beide Pole erfüllen Systemfunktion?
- ✓ Kernkollision sichtbar?

**Heute-Signale (H):**
- Pfad/Fristen (2 Punkte)
- Kosten/Preissprung (2 Punkte)
- Barrieren (2 Punkte)
- Kleinere Einkommen stärker belastet (2 Punkte)
- Schutzlücke (2 Punkte)

**Label-Berechnung:**
- **ZENTRAL:** Q ≥ 2 & H ≥ 7
- **PRÜFKANDIDAT:** H 3-6
- **HINTERGRUND:** sonst

---

### **4. Speicher & Export**

**Lokale Speicherung:**
- Alle ZKs in Browser LocalStorage
- ~500-1000 ZKs möglich
- Bleibt erhalten nach Browser-Neustart

**CSV-Export:**
```csv
Nr,Pol A,Pol B,Label,Q1,Q2,Zeit,Kosten,Barrieren,Schere,Lücke,H-Score,Timestamp
1,"Kostenorientierte Medizinethik","Unbedingter Lebensschutz",ZENTRAL,nein,nein,nein,ja,ja,nein,ja,8,"14.11. 13:10"
```

→ Importierbar in Excel/R/Python für weitere Analyse

---

## 📊 Use Cases

### **Policy-Screening (50 Texte)**
- 30 einfache (Pattern) + 20 komplexe (KI)
- Zeit: ~30 Min
- CSV-Export → Excel-Analyse → Identifikation von 5 ZENTRAL-Fällen

### **Workshop-Vorbereitung**
- 10 ZKs vorbereiten & speichern
- Live durchklicken mit "Laden"-Button
- CSV für Handouts

### **Forschung (3 Monate)**
- Kontinuierlich ZKs sammeln
- Export → Clustering-Analyse in R/Python

---

## 🤖 KI-Integration

### **Wann wird KI genutzt?**

**Pattern-Matching reicht für:**
- "Ohne X kein Y" → Förderung ↔ Fortschritt
- "Zwischen X und Y" → Klimaschutz ↔ Wirtschaft
- Klar strukturierte Policy-Texte

**KI nötig für:**
- Ethische Debatten (Sterbehilfe, Altersrationierung)
- Medienberichte mit Pro/Contra
- Texte ohne klare Muster

**User entscheidet:**
```
⚠️ Kein klares Muster erkannt
[🤖 KI-Analyse starten (2-3s)] [✋ Manuell eingeben]
```

---

## 💰 Kosten

**GitHub Pages Hosting:** Kostenlos ✅

**Claude API:**
- Funktioniert über claude.ai (kein API-Key nötig)
- ~$0.003 pro KI-Analyse
- Realistisch: 20-50 Analysen/Monat = **~$0.15/Monat**
- Praktisch: **Vernachlässigbar**

---

## 🔧 Technische Details

**Stack:**
- Vanilla HTML/CSS/JavaScript (kein Framework)
- Claude API (Sonnet 4)
- LocalStorage für Persistenz
- Responsive Design (Desktop + Mobile)

**Browser-Kompatibilität:**
- Chrome/Edge: ✅
- Firefox: ✅
- Safari: ✅

**Offline-Fähigkeit:**
- Pattern-Matching: ✅ (funktioniert offline)
- KI-Analyse: ❌ (braucht Internet)
- Gespeicherte ZKs: ✅ (lokal verfügbar)

---

## 📝 Changelog

### **v7.1 (2025-11-14)**
- ✨ KI-gestützte Pol-Extraktion (Claude API)
- ✨ 3-Stufen-Ansatz (Pattern → Quality → KI)
- ✨ Erweiterte Refinement-Patterns (Medizinethik)
- 🐛 Fix: Scroll-Problem in rechter Spalte

### **v6.0 (2025-11-14)**
- ✨ Speicher-System (LocalStorage)
- ✨ CSV-Export
- ✨ Laden/Löschen gespeicherter ZKs

### **v5.x (2025-11-13)**
- ✨ Pattern-Matching ("Ohne X kein Y")
- ✨ Refinement-Buttons
- ✨ Auto-Analyse nach Refinement

---

## 🎓 Hintergrund: ZK-RK-Projekt

Dieses Tool ist Teil des **ZK-RK-Forschungsprojekts** (Zielkonflikte - Radikale Kompromisse), das bis März/April 2026 läuft.

**Ziel:** Systematische Analyse von Zielkonflikten in deutscher Transformationspolitik zur Ermöglichung "radikaler Kompromisse" für erfolgreiche gesellschaftliche Transformation.

**Methodik:** 
- 19 identifizierte Zielkonflikte
- 10 Aktionsfelder
- "3-YES-Regel" zur Kategorisierung
- Interaktive App + Workshops + Buchprojekt

---

## 📫 Kontakt & Beitrag

**Fragen oder Feedback?**
- GitHub Issues: [github.com/burmeister12439-futur2/zk-generator/issues](https://github.com/burmeister12439-futur2/zk-generator/issues)

**Beiträge willkommen:**
- Pull Requests für neue Refinement-Patterns
- Bug-Reports
- Feature-Requests

---

## 📄 Lizenz

Dieses Projekt ist für Forschungs- und Bildungszwecke frei nutzbar.

---

**Entwickelt für das ZK-RK-Projekt | November 2025**
