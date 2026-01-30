## 🚀 **Computer Vision Projekt: CIFAR-10 Klassifikation mit Transfer Learning**

## 📋 **Projektübersicht**

Dieses Projekt implementiert eine **Bildklassifikations-Pipeline** für den CIFAR-10-Datensatz unter Verwendung von **Transfer Learning mit ResNet50**. Das Ziel ist es, 10 verschiedene Objektklassen in 32x32 Pixel großen RGB-Bildern zu klassifizieren.

**🔗 Projekt in Google- Drive:** https://drive

---

## 🎯 **Projektziele**

1. **Datenvorverarbeitung** des CIFAR-10-Datensatzes
2. **Implementierung** eines Transfer-Learning-Ansatzes mit ResNet50
3. **Training und Fine-Tuning** eines benutzerdefinierten Klassifikationskopfes
4. **Evaluierung** der Modellperformance
5. **Dokumentation** aller Schritte und Erkenntnisse

---

## 📊 **Datensatz: CIFAR-10**

- **60.000 Bilder** (50.000 Training, 10.000 Test)
- **32x32 Pixel** Auflösung
- **3 Farbkanäle** (RGB)
- **10 Klassen**:
  - ✈️ Flugzeug
  - 🚗 Automobil  
  - 🐦 Vogel
  - 🐱 Katze
  - 🦌 Hirsch
  - 🐕 Hund
  - 🐸 Frosch
  - 🐴 Pferd
  - 🚢 Schiff
  - 🚚 Lastwagen

**Projektbegrenzung:** 10.000 Trainingsbilder für kürzere Trainingszeiten.

---

## 🏗️ **Technischer Stack**

### 📚 Hauptbibliotheken
- **TensorFlow 2.x** & **Keras** - Deep Learning Framework
- **ResNet50** - Vortrainiertes CNN für Transfer Learning
- **NumPy** - Numerische Berechnungen
- **Matplotlib** & **Seaborn** - Visualisierung
- **Scikit-learn** - Metriken und Evaluation
- **Pandas** - Datenanalyse

### ☁️ Plattform
- **Google Colab** - Cloud-basierte Entwicklung
- **Google Drive** - Datenspeicherung
- **GPU/TPU Beschleunigung** - Schnelleres Training

---

## 📁 **Projektstruktur**

### Ordner-Hierarchie


````

ComputerVisionProjekt/
├── 1_Download/ # Rohdaten des CIFAR-10 Datensatzes
├── 2_Data_Preprocessing/ # Vorverarbeitete Daten für ResNet50
├── 3_Model_Architecture/ # Modellarchitektur und Konfiguration
├── 4_Training_Head/ # Training des benutzerdefinierten Kopfes
├── 5_Fine_Tuning/ # Fine-Tuning des Basismodells
├── 6_Evaluation/ # Evaluierungsmetriken und Ergebnisse
├── 7_Results/ # Finale Ergebnisse und Modelle
└── 8_Visualizations/ # Grafiken und Visualisierungen

````




**Alle Daten werden automatisch in deinem Google Drive gespeichert!**

---

## 🔄 Arbeitsablauf im Notebook

### **Phase 1: Setup & Daten** ✅
1. **Google Drive verbinden** - Persistente Datenspeicherung
2. **Bibliotheken installieren** - TensorFlow, NumPy, Matplotlib, etc.
3. **CIFAR-10 laden** - 10.000 Samples für Training
4. **Daten speichern** - Automatisch in Google Drive

### **Phase 2: Vorverarbeitung** ✅
1. **Normalisierung** - Bilder auf [0, 1] skalieren
2. **One-Hot Encoding** - Labels für Keras vorbereiten
3. **ResNet50 Preprocessing** - `preprocess_input()` anwenden
4. **Visualisierung** - Beispieldaten anzeigen

### **Phase 3: Modellaufbau** ✅
1. **ResNet50 Basismodell** - Mit ImageNet Gewichten laden
2. **Custom Head Design** - Dense Layers mit Dropout/BatchNorm
3. **Modell kompilieren** - Adam Optimizer, Categorical Crossentropy

### **Phase 4: Training** 🏋️
1. **Head Training (10 Epochen)** - Nur Custom Layers trainieren
2. **Fine-Tuning (10 Epochen)** - Basismodell mit trainieren
3. **Callbacks** - EarlyStopping, ModelCheckpoint, ReduceLROnPlateau

### **Phase 5: Evaluation** 📈
1. **Test Performance** - Accuracy und Loss auf Testdaten
2. **Konfusionsmatrix** - Detailierte Klassifikationsanalyse
3. **Vorhersage-Beispiele** - Richtig/Falsch klassifizierte Bilder

### **Phase 6: Dokumentation** 📝
1. **Training History Plots** - Accuracy/Loss Entwicklung
2. **Modelle speichern** - Bestes Modell als .h5 Datei
3. **Ergebnisvisualisierung** - Alle Grafiken exportieren
4. **Daten sichern** - Alles in Google Drive speichern

---

## 🎯 Wichtige Ergebnisse

### **Training Performance:**
- **Head Training**: ~60-70% Validation Accuracy
- **Fine-Tuning**: ~75-85% Validation Accuracy  
- **Test Accuracy**: Ziel ~80% auf ungesehenen Daten

### **Modellarchitektur:**


### **Technische Details:**
- **Optimizer**: Adam (learning_rate=0.001)
- **Loss**: Categorical Crossentropy
- **Batch Size**: 32
- **Epochen**: 10 + 10
- **Validation Split**: 20%

---

## ⚡ Google Colab Tipps

### **Hardware beschleunigen:**
1. Klicke auf **"Laufzeit"** → **"Laufzeittyp ändern"**
2. Wähle **"GPU"** oder **"TPU"** als Hardwarebeschleuniger
3. Klicke auf **"Speichern"**

### **Bei Performance-Problemen:**
- **Batch Size reduzieren** (z.B. von 32 auf 16)
- **EarlyStopping aktivieren** um Epochen zu sparen
- **Nur 5.000 Samples** statt 10.000 verwenden

### **Daten speichern & laden:**
# python
# Alle Daten sind hier gespeichert:
base_path = "/content/drive/MyDrive/"
