# 🚀 Flutter Setup Guide für Anfänger

## ✅ Schritt 1: Flutter SDK Herunterladen & Installieren

### **Windows:**

1. Gehe zu https://flutter.dev/docs/get-started/install/windows
2. Klicke auf **"Download Flutter SDK"** (neueste stabile Version)
3. Entpacke die `.zip` Datei an einem Ort deiner Wahl:
   ```
   C:\flutter  (empfohlen)
   ```
4. Öffne **PowerShell als Administrator** und führe aus:
   ```powershell
   $env:PATH += ";C:\flutter\bin"
   [Environment]::SetEnvironmentVariable("Path", $env:PATH, "Machine")
   ```
5. Öffne eine **neue PowerShell** und tippe:
   ```powershell
   flutter --version
   ```
   Sollte eine Versionsnummer zeigen (z.B. `Flutter 3.19.0`) ✓

---

### **macOS:**

1. Gehe zu https://flutter.dev/docs/get-started/install/macos
2. Lade **Flutter SDK** herunter
3. Entpacke zu deinem Home-Verzeichnis:
   ```bash
   mkdir ~/development
   cd ~/development
   unzip ~/Downloads/flutter_macos_*.zip
   ```
4. Öffne Terminal und füge Flutter zum PATH hinzu:
   ```bash
   nano ~/.zshrc
   # Oder für ältere Macs:
   nano ~/.bash_profile
   ```
5. Füge diese Zeile ein:
   ```bash
   export PATH="$PATH:~/development/flutter/bin"
   ```
6. Speichern: `Ctrl+O` → `Enter` → `Ctrl+X`
7. Terminal neu starten und testen:
   ```bash
   flutter --version
   ```

---

### **Linux:**

1. Öffne Terminal
2. Lade Flutter herunter:
   ```bash
   cd ~
   git clone https://github.com/flutter/flutter.git
   cd flutter
   git checkout stable
   ```
3. Füge PATH hinzu:
   ```bash
   echo 'export PATH="$PATH:~/flutter/bin"' >> ~/.bashrc
   source ~/.bashrc
   ```
4. Teste:
   ```bash
   flutter --version
   ```

---

## ✅ Schritt 2: System-Anforderungen überprüfen

Tippe in der **Kommandozeile/Terminal**:
```bash
flutter doctor
```

Du solltest ungefähr so etwas sehen:
```
Doctor summary (to see all details run flutter doctor -v):
[✓] Flutter (Channel stable, 3.19.0)
[✗] Android toolchain
[✗] Xcode (macOS only)
[✓] Chrome - develop for the web
[!] Android Studio
[✓] VS Code
[✓] Connected device (1 available)
```

**Rote X (✗)** = Du musst das installieren  
**Grüne Haken (✓)** = Schon vorhanden

---

## ✅ Schritt 3: IDE installieren (VS Code oder Android Studio)

### **Option A: VS Code (Anfänger-freundlich)** ✅ EMPFOHLEN

1. Lade **VS Code** herunter: https://code.visualstudio.com
2. Installiere es
3. Öffne VS Code
4. Gehe zu **Extensions** (linke Seitenleiste)
5. Suche nach **"Flutter"** (von Dart Code)
6. Klicke **Install**
7. Starte VS Code neu

**Fertig!** ✓

---

### **Option B: Android Studio (für später)**

Wenn du später auf echte Android-Phones testen willst:
1. Lade herunter: https://developer.android.com/studio
2. Installiere es
3. Öffne Android Studio → Plugins → Suche "Flutter" → Install
4. Neustart

---

## ✅ Schritt 4: Dein erstes Flutter-Projekt erstellen

Öffne **Terminal/PowerShell** und führe aus:

```bash
flutter create fitness_app
cd fitness_app
```

Das erstellt einen Ordner `fitness_app` mit all dem Basis-Code.

---

## ✅ Schritt 5: App starten & testen

### **Option A: Im Browser (Schnellste Methode)**

```bash
flutter run -d chrome
```

Ein Chrome-Fenster öffnet sich mit einer Demo-App! 🎉

### **Option B: Mit Emulator (Android)**

```bash
flutter emulator
# Wähle einen Emulator
# Dann:
flutter run
```

### **Option C: Mit echtem Phone**

1. Verbinde dein Phone mit USB-Kabel
2. Aktiviere "Developer Mode" (Android: Einstellungen → Über das Telefon → Build-Nummer 7x tippen)
3. Tippe:
   ```bash
   flutter run
   ```

---

## 📁 Projekt-Struktur verstehen

Nach `flutter create fitness_app` siehst du:

```
fitness_app/
├── lib/
│   └── main.dart          ← DEIN CODE (hier schreibst du!)
├── pubspec.yaml           ← Dependencies (Bibliotheken)
├── android/               ← Android-Einstellungen
├── ios/                   ← iOS-Einstellungen (nur macOS)
├── web/                   ← Web-Version
└── test/                  ← Tests
```

**Wichtig:** Du schreibst 99% deinen Code in `lib/main.dart` und danach in `lib/screens/`, `lib/models/`, etc.

---

## 🔧 Wichtige Terminal-Befehle

```bash
# App starten (Browser)
flutter run -d chrome

# Dependencies installieren (nach pubspec.yaml Änderungen)
flutter pub get

# Clean build (wenn Fehler auftreten)
flutter clean
flutter pub get
flutter run

# App debuggen (Mit Hot Reload = Code ändert sich live!)
flutter run

# Build für Produktion
flutter build apk          # Android
flutter build ios          # iOS (macOS only)
flutter build web          # Web
```

---

## 📚 Erste Schritte mit Code

Öffne `lib/main.dart` in VS Code:

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Fitness App',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: const MyHomePage(title: 'Home'),
    );
  }
}

class MyHomePage extends StatefulWidget {
  const MyHomePage({Key? key, required this.title}) : super(key: key);
  final String title;

  @override
  State<MyHomePage> createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text(widget.title),
      ),
      body: const Center(
        child: Text('Willkommen zur Fitness App!'),
      ),
    );
  }
}
```

Speichern (`Ctrl+S`) → Die App aktualisiert sich automatisch! (Hot Reload)

---

## 🐛 Häufige Fehler & Lösungen

| Fehler | Lösung |
|--------|--------|
| `flutter: command not found` | Flutter nicht im PATH. Neustart erforderlich oder Installationsschritte wiederholen |
| `Android toolchain issue` | Tippe `flutter doctor -v` und folge den Anweisungen |
| `Web connection refused` | Port 8000 ist belegt. Tippe `flutter run -d chrome --web-port=8001` |
| `Hot Reload funktioniert nicht` | Speichern mit Ctrl+S, oder `r` in der Kommandozeile drücken |

---

## 📋 Checkliste: Setup abgeschlossen?

- [ ] Flutter SDK heruntergeladen & installiert
- [ ] `flutter --version` zeigt eine Versionsnummer
- [ ] `flutter doctor` zeigt keine kritischen Fehler (✗)
- [ ] VS Code oder Android Studio installiert
- [ ] Erstes Projekt mit `flutter create fitness_app` erstellt
- [ ] App mit `flutter run -d chrome` gestartet
- [ ] "Willkommen zur Fitness App!" sichtbar ✓

---

## 🚀 Jetzt weitermachen!

Nach dieser Checkliste bist du bereit, die Fitness-App zu bauen! 💪

**Nächster Schritt:** Ich erstelle dir eine Basis-Version mit:
- Bottom Navigation Bar
- 4 leere Screens
- Firebase Setup
- Authentifizierung

Bereit? 🎯

---

## 🆘 Noch Fragen?

- Flutter Docs: https://flutter.dev/docs
- Dart Lernen: https://dart.dev/guides
- YouTube: "Flutter Tutorial für Anfänger" (auf Deutsch)
