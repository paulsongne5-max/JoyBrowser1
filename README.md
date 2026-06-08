# JOY Browser 🌐

> **Rapide. Sécurisé. Intelligent.**  
> Le navigateur des nouvelles générations.

---

## 📋 Description

JOY Browser est un navigateur Android complet basé sur **Chromium WebView (Kotlin)**, inspiré de Brave Browser et Google Chrome. Conçu pour offrir une navigation rapide, sécurisée et optimisée pour les réseaux faibles.

---

## 🚀 Fonctionnalités

| Fonctionnalité | Statut |
|---|---|
| Navigation WebView complète | ✅ |
| Barre d'URL intelligente | ✅ |
| Multi-onglets | ✅ |
| Favoris (Bookmarks) | ✅ |
| Historique de navigation | ✅ |
| Téléchargement de fichiers | ✅ |
| **Bloqueur de publicités** | ✅ |
| **Protection anti-tracking** | ✅ |
| Mode navigation privée | ✅ |
| Alerte sites dangereux | ✅ |
| Mode économie de données | ✅ |
| Mode bureau | ✅ |
| Interface sombre | ✅ |
| Barre d'outils en bas | ✅ |

---

## ⚙️ Configuration requise

- **Android Studio** : Hedgehog (2023.1.1) ou supérieur
- **JDK** : 17+
- **SDK Android minimum** : API 21 (Android 5.0)
- **SDK cible** : API 34 (Android 14)

---

## 🛠️ Installation & Compilation

### Étape 1 — Cloner / Ouvrir le projet

Ouvrez Android Studio → **File > Open** → sélectionner le dossier `JoyBrowser/`

### Étape 2 — Ajouter les polices Poppins

Télécharger sur [Google Fonts — Poppins](https://fonts.google.com/specimen/Poppins) :

Placer dans `app/src/main/res/font/` :
```
poppins_bold.ttf       (weight 700)
poppins_medium.ttf     (weight 500)
poppins_regular.ttf    (weight 400)
```

> **Astuce** : Dans Android Studio → `res/font` → clic droit → **Add font from font** (téléchargement automatique).

### Étape 3 — Synchroniser Gradle

```
File > Sync Project with Gradle Files
```

### Étape 4 — Compiler l'APK

```
Build > Build Bundle(s) / APK(s) > Build APK(s)
```

L'APK sera dans :  
`app/build/outputs/apk/debug/app-debug.apk`

---

## 📁 Structure du projet

```
JoyBrowser/
├── app/src/main/
│   ├── java/com/joybrowser/browser/
│   │   ├── JoyBrowserApp.kt              # Application class
│   │   ├── data/
│   │   │   ├── local/
│   │   │   │   ├── JoyDatabase.kt        # Room Database
│   │   │   │   ├── dao/                  # DAOs (Bookmark, History, Download)
│   │   │   │   └── entities/             # Entités Room
│   │   │   └── preferences/
│   │   │       └── UserPreferences.kt    # DataStore Preferences
│   │   ├── model/
│   │   │   └── BrowserTab.kt             # Modèle d'onglet
│   │   ├── service/
│   │   │   └── DownloadService.kt        # Service de téléchargement
│   │   ├── ui/
│   │   │   ├── activities/
│   │   │   │   ├── MainActivity.kt       # Activité principale
│   │   │   │   ├── SettingsActivity.kt   # Paramètres
│   │   │   │   ├── DownloadsActivity.kt  # Téléchargements/Historique/Favoris
│   │   │   │   ├── JoyWebViewClient.kt   # Client WebView + ad-block
│   │   │   │   └── JoyWebChromeClient.kt # Chrome WebView
│   │   │   └── dialogs/
│   │   │       └── TabsDialog.kt         # Gestionnaire d'onglets
│   │   ├── utils/
│   │   │   ├── AdBlocker.kt             # Moteur de blocage publicitaire
│   │   │   └── UrlUtils.kt             # Utilitaires URL
│   │   └── viewmodel/
│   │       └── BrowserViewModel.kt      # ViewModel principal
│   ├── res/
│   │   ├── drawable/                     # Icônes vectoriels
│   │   ├── layout/                       # Layouts XML
│   │   ├── values/                       # Couleurs, thèmes, strings
│   │   └── xml/                          # Config files
│   └── AndroidManifest.xml
├── build.gradle
├── settings.gradle
└── README.md
```

---

## 🎨 Design System

| Élément | Valeur |
|---|---|
| Couleur principale | `#FF6A00` (Orange JOY) |
| Fond primaire | `#0F0F10` |
| Fond secondaire | `#1F1F22` |
| Texte principal | `#FFFFFF` |
| Police | Poppins (Bold / Medium / Regular) |
| Mode | Sombre par défaut |

---

## 🛡️ Système AdBlock

Le moteur de blocage `AdBlocker.kt` bloque :
- **+40 domaines publicitaires** majeurs (Google Ads, Facebook Ads, Taboola, Criteo, etc.)
- **Patterns de tracking** (Google Analytics, Mixpanel, Hotjar, Heap, etc.)
- Support d'une **liste personnalisée** chargée depuis `assets/blocklist.txt`

### Ajouter une liste de filtres (EasyList)
Télécharger [EasyList](https://easylist.to/) au format hosts et placer dans :
```
app/src/main/assets/blocklist.txt
```

---

## 🔧 Personnalisation

### Moteurs de recherche disponibles
- Google (défaut)
- Bing
- DuckDuckGo
- Yahoo
- Brave Search

### Page d'accueil
La page d'accueil est générée en HTML dans `MainActivity.getHomePageHtml()`.  
Personnalisable : liens rapides, stats de protection, design.

---

## 📝 Licence

JOY Browser — Tous droits réservés © 2024  
Développé avec ❤️ pour les utilisateurs africains et mondiaux.

---

*Rapide. Sécurisé. Intelligent. — Le navigateur des nouvelles générations.*
