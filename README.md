
# My Notes - Complete Project Documentation

## "Let Me Note, What You Did...!"

---

## 📱 Project Overview

**My Notes** is a personal journal application designed to help users document and remember the events of their lives. Every note represents a moment, a memory, or an event worth keeping.

### Key Differentiators

- **100% Offline** — No internet required. All data stays on device.
- **Privacy First** — No tracking. No ads. No cloud dependency.
- **Urdu Support** — Full RTL support for Urdu notes and PDFs.
- **PDF Generation** — Professional, multi-page PDFs with proper formatting.
- **Cross-Version Compatible** — Works on Android 7.0 to 16+.
- **Backup & Restore** — Export/Import notes as JSON.

### Tagline
> *"Let Me Note, What You Did...!"*

---

## 📋 Feature Checklist

### Core Features

| Feature | Status | Description |
|---------|--------|-------------|
| Splash Screen | ✅ | App icon, name, tagline, loading bar |
| Signup Screen | ✅ | Name, Contact, Email, Continue/Skip |
| Main Screen | ✅ | App name, Settings icon, Notes list, FAB |
| Note Editor | ✅ | Create, Edit, View notes |
| Swipe Left | ✅ | Permanent delete (no confirm, no undo) |
| Swipe Right | ✅ | Confirm dialog + Undo snackbar |
| Long Press | ✅ | Generate PDF from note |
| Search Notes | ✅ | Search by title and content |

### Settings

| Feature | Status | Description |
|---------|--------|-------------|
| Profile View | ✅ | View user info (read-only) |
| Profile Edit | ✅ | Edit name, contact, email |
| Theme Mode | ✅ | Light, Dark, System |
| Bold Font | ✅ | Toggle bold text |
| Font Size | ✅ | Small, Medium, Large, X-Large |
| Font Style | ✅ | Roboto, Open Sans |
| Sort Order | ✅ | Newest First, Oldest First, Title A-Z |
| View Mode | ✅ | List View, Grid View |
| Confirm Delete | ✅ | Toggle delete confirmation |
| Auto-Save | ✅ | Auto-save draft while editing |
| Date Format | ✅ | DD/MM/YYYY, MM/DD/YYYY, YYYY-MM-DD |
| Week Start | ✅ | Monday, Sunday |
| Export Notes | ✅ | Export all notes as JSON |
| Import Notes | ✅ | Import notes from JSON backup |
| Clear All Data | ✅ | Reset app with confirmation |
| App Info | ✅ | About app section |
| Developer Info | ✅ | Developer information |

### PDF Generator

| Feature | Status | Description |
|---------|--------|-------------|
| Multi-Page Support | ✅ | Auto-creates new pages |
| Page Numbers | ✅ | "Page X of Y" at bottom |
| Header | ✅ | App name + tagline on every page |
| Footer | ✅ | Export date, Event date, Page number |
| Urdu RTL | ✅ | Full right-to-left alignment |
| Word Wrapping | ✅ | Proper content wrapping |
| Auto-Open | ✅ | Opens PDF after generation |
| File Location | ✅ | Documents/MyNotes/ |

### Technology

| Component | Technology |
|-----------|------------|
| UI | XML layouts |
| Language | Java |
| Database | SQLite |
| PDF Generation | PdfDocument (Android built-in) |
| Minimum SDK | API 24 (Android 7.0) |
| Target SDK | API 35+ (Android 16+) |

---
### Database Schema

#### Notes Table

| Column | Type | Description |
|--------|------|-------------|
| `id` | INTEGER PRIMARY KEY | Auto-increment |
| `title` | TEXT | Note title |
| `content` | TEXT | Note content |
| `event_date` | INTEGER | Event date timestamp |
| `created_date` | INTEGER | Creation timestamp |
| `last_modified` | INTEGER | Last modified timestamp |

#### User Table

| Column | Type | Description |
|--------|------|-------------|
| `id` | INTEGER PRIMARY KEY | Auto-increment |
| `name` | TEXT | User name |
| `contact` | TEXT | User contact |
| `email` | TEXT | User email |
| `signup_date` | INTEGER | Signup timestamp |
| `is_skipped` | INTEGER | 0=full, 1=skipped |
| `expiry_date` | INTEGER | Expiry for skip users |

#### Settings Table

| Column | Type | Description |
|--------|------|-------------|
| `key` | TEXT PRIMARY KEY | Setting key |
| `value` | TEXT | Setting value |
| `updated_at` | INTEGER | Last updated timestamp |

---

## 📚 User Guide

### Getting Started

1. **Download** My Notes from the Play Store
2. **Open** the app → Splash Screen appears
3. **Sign up** with Name, Contact, Email (all three for permanent access)
4. **Read** the default welcome note
5. **Start** adding your events

### Creating a Note

1. Tap the **+ FAB** button at the bottom right
2. Enter **Title** and **Content**
3. Select **Event Date** (tap the date field)
4. Tap **Save**

### Viewing a Note

1. Tap any **note card** on the main screen
2. The note opens in **View Mode** (read-only)
3. Tap the **Edit Icon** (pencil) to edit

### Editing a Note

1. In Edit Mode, modify **Title**, **Content**, or **Event Date**
2. Tap **Save** to keep changes
3. Tap **Cancel** to discard changes (shows "Nothing saved")

### Deleting a Note

| Action | Result |
|--------|--------|
| **Swipe Left** | Immediate delete (no confirm, no undo) |
| **Swipe Right** | Confirm dialog → delete → undo option for 5 seconds |

### Generating a PDF

1. **Long press** any note card
2. Tap **Generate PDF**
3. PDF saves to `Documents/MyNotes/`
4. PDF auto-opens in default viewer

### Exporting Notes (Backup)

1. Go to **Settings → Backup & Delete**
2. Tap **Export All Notes**
3. JSON file saved to `Documents/MyNotes/`

### Importing Notes (Restore)

1. Copy JSON backup file to device
2. Go to **Settings → Backup & Delete**
3. Tap **Import Notes**
4. Select the JSON file

### Customizing the App

- **Theme:** Settings → Theme Mode (Light/Dark/System)
- **Font:** Settings → Readability (Bold, Size, Style)
- **Behavior:** Settings → Behavior (Sort, View, Confirm, Auto-save, Date, Week)
- **Profile:** Settings → View/Edit Profile

---

## 🌐 Urdu Language Support

### Urdu Features

| Feature | Implementation |
|---------|----------------|
| Urdu Note Content | ✅ Fully supported |
| Urdu Note Titles | ✅ Fully supported |
| Urdu PDF Export | ✅ Full RTL alignment |
| Urdu PDF Header | ✅ RTL app name and tagline |
| Urdu PDF Dates | ✅ English format (clear and consistent) |
| Word Integrity | ✅ No broken words (no hyphenation) |

### Urdu Detection

```java
private static final Pattern URDU_PATTERN = 
    Pattern.compile("[\\u0600-\\u06FF\\u0750-\\u077F\\u08A0-\\u08FF\\uFB50-\\uFDFF\\uFE70-\\uFEFF]");
```

---

## 📱 Android Compatibility

| Android Version | API Level | Compatibility |
|-----------------|-----------|---------------|
| 7.0 (Nougat) | 24 | ✅ Full support |
| 8.0 (Oreo) | 26-27 | ✅ Full support |
| 9.0 (Pie) | 28 | ✅ Full support |
| 10.0 (Q) | 29 | ✅ Full support |
| 11.0+ | 30-35+ | ✅ Full support |

### Storage Handling

| Android Version | Save Method | Location |
|-----------------|-------------|----------|
| 7-9 | Legacy File API | Documents/MyNotes/ |
| 10+ | MediaStore | Documents/MyNotes/ |

---

## 🔒 Privacy & Permissions

### Permissions

| Permission | Android Version | Purpose |
|------------|-----------------|---------|
| `WRITE_EXTERNAL_STORAGE` | 7-9 | Save PDFs to Documents/ |
| `READ_EXTERNAL_STORAGE` | 7-9 | Read backup files |
| `ACCESS_MEDIA_LOCATION` | 10+ | Scoped storage access |

### Privacy Promise

| Aspect | Status |
|--------|--------|
| Internet Access | ❌ Not required |
| User Tracking | ❌ None |
| Ads | ❌ None |
| Cloud Storage | ❌ None |
| Data Collection | ❌ None |
| All Data Local | ✅ Yes |

---

### PDF Specifications

| Element | Specification |
|---------|---------------|
| Page Size | A4 (595 x 842 points) |
| Margins | Left 60, Right 60, Top 50, Bottom 50 |
| App Name | Bold, 16pt |
| Tagline | Italic, 11pt |
| Title | Bold, 18pt |
| Content | Regular, 12pt, Justified |
| Footer | Regular, 10pt |
| Urdu Support | Full RTL alignment |

---

## 📊 App Metadata

| Field | Value |
|-------|-------|
| **App Name** | My Notes |
| **Tagline** | Let Me Note, What You Did...! |
| **Developer** | Syed Muhammad Sajawal Hussain |
| **Version** | 1.0 |
| **Category** | Productivity / Journal |
| **Price** | Free |
| **Ads** | None |
| **In-app Purchases** | None |
| **Internet** | Not required |

---

## 🎯 Use Cases

### 1. Personal Journal

**Person-1:**

> *"Person-1 writes about daily life, milestones, and memories."*

---

### 2. Event Documentation

**Person-2:**

> *"Person-2 records graduation day with date and detailed description."*

---

### 3. Urdu Journaling

**Person-3:**

> *"Person-3 writes childhood memories in Urdu."*

---

### 4. PDF Sharing

**Person-4:**

> *"Person-4 generates PDF of graduation note and shares with family."*

---

### 5. Phone Transition

**Person-5:**

> *"Person-5 exports notes from old Android 8 phone and imports to new Android 16+."*

---

### 6. Backup & Restore

**Person-6:**

> *"Person-6 backs up all notes before factory reset and restores after."*
---

## 🛠️ Development Notes

### Naming Conventions

| File Type | Naming Rule | Example |
|-----------|-------------|---------|
| Layout XML | `activity_name.xml` | `activity_main.xml` |
| Java Class | `Name.java` | `MainActivity.java` |
| Model Class | `Modelname.java` | `ModelNote.java` |
| Adapter Class | `Adaptername.java` | `AdapterNote.java` |

### Code Style

- Java with AndroidX AppCompat
- SQLite with raw queries
- XML with ConstraintLayout
- Black and gray color scheme
- No emojis — XML drawable icons

---

## 📝 Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | June 2026 | Initial release |

---

## 👨‍💻 Developer

**Syed Muhammad Sajawal Hussain**

- Vision: Simple, private, and meaningful digital tools
- Focus: Privacy, Urdu support, Cross-version compatibility

---

## 📄 License

© 2026 My Notes. All rights reserved.

---

## 🙏 Acknowledgments

Thank you to all users who trust My Notes with their memories.

Every event needs to be noted.
Every memory needs to be kept.
Every story must be remembered.

---

**End of Documentation**

*"Let Me Note, What You Did...!"*
```
