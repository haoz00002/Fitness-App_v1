# 🏋️ Flutter Fitness & Regeneration App - 1 Monat Entwicklungsplan

## 📋 Projekt-Übersicht
- **Zeitrahmen:** 4 Wochen (28 Tage)
- **Ziel:** MVP (Minimum Viable Product) mit Kern-Features
- **Priorität:** Funktionalität > Perfektion
- **Backend:** Google Firebase (Authentication, Firestore, Storage)

---

## 🎯 MVP-Features (Priorisiert nach Wichtigkeit)

### ✅ MUSS-HABEN (Woche 1-2)
1. **Authentication & Onboarding**
   - Sign-Up mit Email/Password
   - Firebase Authentication
   - Einfaches Profil-Setup (Name, Alter, Gewicht)

2. **Home Screen (Reduziert)**
   - Level/XP-Display (statisch mit Dummy-Daten)
   - 2-3 Regenerations-Cards (Beine, Oberkörper, Core)
   - Progress-Balken
   - "Training starten" Button

3. **Übungs-Katalog (Minimal)**
   - Liste von 10-15 vordefinierten Übungen
   - Einfache Kategorisierung (3 Muskelgruppen max.)
   - Keine komplexen Filter

### 🔄 SOLLTE-HABEN (Woche 2-3)
4. **Training Tracking Basis**
   - Übung starten → Timer + Set/Rep Counter
   - Gewicht eingeben (optional)
   - Training speichern (lokal + Firebase)

5. **Trainings-Kalender (Simplified)**
   - Monatsübersicht
   - Anzeige trainierter Tage (einfache Dots)
   - Keine komplexen Heatmaps

6. **Einfache Statistiken**
   - Trainings-Counter (diesen Monat)
   - Gesamte Trainingszeit
   - Häufigste Übung

### 🌟 NICE-TO-HAVE (Woche 4 / Wenn Zeit)
7. **Regenerations-Simulation**
   - Regenerationsstatus steigt über Zeit
   - Bei Training sinkt der Status temporär
8. **Favorit-System**
   - Favoriten speichern
9. **Basis-Benachrichtigungen**
   - Einfache Push-Notif bei Training

---

## 📅 Detaillierter Wochenplan

### **WOCHE 1: Setup & Authentication**
**Ziel:** Authentifiziertes Projekt mit Basis-Navigation

#### Tag 1-2: Project Setup
- [ ] Flutter-Projekt erstellen
- [ ] Dependencies installieren:
  ```yaml
  dependencies:
    firebase_core: ^latest
    firebase_auth: ^latest
    cloud_firestore: ^latest
    provider: ^6.0.0  # State Management
    intl: ^0.18.0     # Datum-Formatierung
  ```
- [ ] Firebase Project erstellen (Google Console)
- [ ] Firebase mit Flutter verbinden (iOS + Android)
- [ ] Basis-Folder-Struktur:
  ```
  lib/
  ├── screens/
  │   ├── auth/
  │   ├── home/
  │   ├── exercises/
  │   ├── calendar/
  │   └── analytics/
  ├── models/
  ├── services/
  ├── widgets/
  └── main.dart
  ```

#### Tag 3-4: Authentication
- [ ] Firebase Auth Service erstellen
- [ ] Sign-Up Screen (Email + Password + Name)
- [ ] Sign-In Screen
- [ ] Basic Error-Handling
- [ ] Persistenz (User bleibt eingeloggt)

#### Tag 5-7: Navigation & Scaffolding
- [ ] Bottom Navigation Bar
- [ ] 4 Basis-Screens (Shells/Placeholders)
- [ ] App-Theme definieren (Farben, Fonts)
- [ ] Splash Screen

**Checkpoint:** Authentifizierung funktioniert, Bottom Nav navigiert ✓

---

### **WOCHE 2: Home & Exercise Screens**
**Ziel:** Basis Home-Screen & Übungs-Katalog

#### Tag 8-9: Home Screen
- [ ] Level-Card UI
- [ ] Regenerations-Grid (4 Muskelgruppen)
- [ ] Dummy-Daten einbauen (später Firebase)
- [ ] Farb-Codierung (Grün/Orange/Rot)
- [ ] "Training starten" Button (navigiert zu Training-Screen)

#### Tag 10-12: Exercise Screen
- [ ] Model `Exercise` erstellen
- [ ] 15 Test-Übungen mit Dummy-Daten
- [ ] Exercise List View
- [ ] Filter-Chips (Alle, Beine, Oberkörper, Core)
- [ ] Search-Funktion (lokal)
- [ ] Play-Button → führt zu Training-Screen

#### Tag 13-14: Training Screen (Neuer Screen)
- [ ] Übungs-Detail anzeigen
- [ ] Set/Rep Counter UI
- [ ] Gewicht Input (Optional)
- [ ] Timer (einfach: 60 Sekunden)
- [ ] "Training abschließen" Button
- [ ] Lokal speichern (SharedPreferences für MVP)

**Checkpoint:** Home Screen sieht gut aus, Übungs-Katalog funktioniert ✓

---

### **WOCHE 3: Calendar & Persistence**
**Ziel:** Trainings-Kalender + Firebase Integration

#### Tag 15-17: Calendar Screen
- [ ] Kalender-Grid (7×6)
- [ ] Aktuelle Trainings-Tage markieren
- [ ] Einfache Punkte (ohne komplexe Heatmap)
- [ ] Tap auf Tag → Trainings-Details zeigen
- [ ] Basis-Statistik (z.B. "18/31 Trainings diesen Monat")

#### Tag 18-20: Firebase Integration
- [ ] `User` Model + Service
- [ ] `Workout` Model + Firestore Collection
- [ ] Training-Daten zu Firebase speichern
- [ ] Trainings-Historie laden
- [ ] Fehlerbehandlung

#### Tag 21: Regenerations-Logik
- [ ] `UserStats` Model (Level, XP, Regenerations-Status)
- [ ] Basis-Berechnung: Regen-Status steigt täglich, sinkt bei Training
- [ ] Lokal cachen (schneller)

**Checkpoint:** Daten fließen zu Firebase, Calendar zeigt Trainings ✓

---

### **WOCHE 4: Analytics & Polish**
**Ziel:** Statistiken + Bug-Fixes + App-Polish

#### Tag 22-23: Analytics Screen
- [ ] 3 KPI-Cards (Trainings, Zeit, Übungen) - statische Daten
- [ ] Einfaches Bar-Chart (Library: `fl_chart` oder `charts_flutter`)
- [ ] Muskelgruppen-Breakdown als horizontale Balken
- [ ] "Top 3 Übungen" Liste

#### Tag 24-25: Polish & Bug-Fixes
- [ ] Loading-States (CircularProgressIndicator)
- [ ] Error-Handling & Messages
- [ ] Responsivität testen (verschiedene Phone-Größen)
- [ ] Basis-Validierung (leere Felder, etc.)

#### Tag 26-27: Testing & Deployment Prep
- [ ] Manuelles Testen aller Flows
- [ ] Firebase Rules konfigurieren (Security)
- [ ] Release-Build erstellen
- [ ] Auf Test-Device deployen

#### Tag 28: Reserve / Finale Touches
- [ ] Last-Minute Bug-Fixes
- [ ] Performance-Optimierung
- [ ] README.md schreiben
- [ ] GitHub Pages für Wireframes

**Checkpoint:** App läuft end-to-end, Firebase funktioniert ✓

---

## 🏗️ Minimales Data Model (Firestore)

### Collection: `users/{uid}`
```json
{
  "uid": "user123",
  "email": "user@gmail.com",
  "name": "Max Mustermann",
  "level": 12,
  "xp": 2450,
  "createdAt": "2026-07-01T10:00:00Z",
  "regenerationStatus": {
    "legs": 78,
    "chest": 45,
    "glutes": 12,
    "core": 65
  }
}
```

### Collection: `users/{uid}/workouts`
```json
{
  "id": "workout123",
  "exerciseId": "ex_pushup",
  "exerciseName": "Liegestütze",
  "muscleGroup": "chest",
  "sets": 3,
  "reps": 12,
  "weight": 0,
  "duration": 180,  // Sekunden
  "createdAt": "2026-07-15T14:30:00Z"
}
```

### Collection: `exercises` (Read-Only / Seeded)
```json
{
  "id": "ex_pushup",
  "name": "Liegestütze",
  "muscleGroup": "chest",
  "description": "Oberkörper-Übung",
  "difficulty": "beginner",
  "defaultReps": 12,
  "imageUrl": "..."
}
```

---

## 🛠️ Tech Stack (Finalisiert)

| Bereich | Technologie | Grund |
|---------|------------|-------|
| **Frontend** | Flutter 3.x | Cross-Platform |
| **State Mgmt** | Provider | Einfach & effektiv |
| **Backend** | Firebase (Auth + Firestore) | Schnelle Integration, Kostenlos |
| **Database** | Cloud Firestore | Real-time, Skalierbar |
| **Charts** | fl_chart | Einfache Integration |
| **Local Cache** | SharedPreferences | Schnell, offline |
| **Deployment** | Google Play + App Store | Später möglich |

---

## 📊 Realistisches Tempo

- **Tägliche Ziel:** 2-3 Stunden produktive Codierung
- **Buffer:** Woche 4 für Bugs & Überraschungen
- **Nicht-Funktionales:** Tests, Deployment-Prep, Dokumentation

---

## 🚀 MVP-Akzeptanzkriterien

✅ App startet ohne Crashes  
✅ User kann sich registrieren & einloggen  
✅ Trainings können gespeichert & geladen werden  
✅ Firebase speichert & lädt Daten korrekt  
✅ Alle 4 Screens sind navigierbar  
✅ Basis-Layout sieht like Wireframes aus  
✅ App funktioniert offline (lokal) & online (Firebase)  

---

## 🔮 Post-MVP Roadmap (Woche 5+)

1. Regenerations-Simulation + XP-System ausbauen
2. Favoriten-System
3. Push-Benachrichtigungen
4. Social Features (Freunde, Challenges)
5. Detaillierte Charts & Analytics
6. Wearable-Integration (Apple Watch, Fitbit)
7. App Store Publishing

---

## 💡 Pro-Tipps zur Zeit-Optimierung

1. **Copy-Paste Courage:** Dupliziere UI-Code statt alles neu zu bauen
2. **Dummy-Daten:** Verwende feste Werte bis Firebase 100% bereit ist
3. **One Screen at a Time:** Nicht alle gleichzeitig anfangen
4. **Git Early, Git Often:** Committe täglich (Backup!)
5. **Flutter Pub:** Nutze externe Packages (keine Zeit für Custom-Widgets)
6. **Figma → Code:** Nutze Flutter-Figma-Plugins für schnellere Code-Gen

---

**Los geht's! 🚀**
