# 🏛️ Walk Through History — AI Travel Planner

<div align="center">

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python&logoColor=white)
![Tkinter](https://img.shields.io/badge/Tkinter-GUI-orange?style=for-the-badge)
![ReportLab](https://img.shields.io/badge/ReportLab-PDF-red?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey?style=for-the-badge)

**A beautifully designed desktop travel planner for India's heritage destinations.**  
Generate personalised day-by-day itineraries, export to PDF, and share with one click.

[Features](#-features) • [Demo](#-demo) • [Installation](#-installation) • [Usage](#-usage) • [Project Structure](#-project-structure) • [Contributing](#-contributing)

</div>

---

## 📸 Demo

> Generate a complete heritage itinerary for any city in India in seconds.

| Form Panel | Generated Itinerary | PDF Export |
|---|---|---|
| Select destination, budget, duration & interests | Day-by-day collapsible itinerary cards | Styled A4 PDF with gold theme |

---

## ✨ Features

- 🗺️ **19 Heritage Destinations** — Covers major cities across North, South, East, West & Central India including Agra, Delhi, Jaipur, Hampi, Varanasi and more
- 🤖 **AI-Style Itinerary Generation** — Animated loading sequence crafts a structured morning / afternoon / evening itinerary for each day
- 📅 **Flexible Duration** — Plans for 2, 3, 5, 7, or 10-day trips
- 💰 **Budget Tiers** — Budget, Mid-range, and Luxury options with per-day cost estimates
- 🎯 **Travel Styles** — Relaxed, Packed, Focused, or Flexible pacing
- 🏷️ **Interest Tags** — Filter experiences by History, Architecture, Food, Photography, Culture, Adventure and more
- 📄 **PDF Export** — Download a fully styled A4 PDF itinerary powered by ReportLab
- 🔗 **HTML Share Link** — Generate a standalone shareable HTML page that opens in your browser
- 🎨 **Dark Gold UI Theme** — Elegant heritage-inspired dark theme built entirely with Tkinter — no web framework needed
- 📱 **Collapsible Day Cards** — Clean accordion-style day-by-day breakdown with time slots and activity tags

---

## 🗺️ Supported Destinations

| Region | Cities |
|---|---|
| **North India** | Agra, Delhi, Varanasi, Lucknow, Amritsar |
| **Rajasthan** | Jaipur, Jodhpur, Udaipur, Jaisalmer |
| **South India** | Hampi, Thanjavur, Madurai, Mysore |
| **West India** | Mumbai, Ajanta & Ellora |
| **East & Central** | Khajuraho, Sanchi, Bhubaneswar |

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| **Python 3.8+** | Core application language |
| **Tkinter** | Desktop GUI framework (built-in) |
| **ttk (Themed Tkinter)** | Styled dropdown / combobox widgets |
| **ReportLab** | PDF generation with custom styling |
| **threading** | Non-blocking loading animation |
| **webbrowser** | Open HTML share page in default browser |
| **tempfile** | Temporary HTML file storage for sharing |

---

## 📦 Installation

### Prerequisites
- Python 3.8 or higher
- pip

### 1. Clone the repository

```bash
git clone https://github.com/your-username/walk-through-history.git
cd walk-through-history
```

### 2. Install dependencies

```bash
pip install reportlab
```

> **Note:** Tkinter comes pre-installed with Python on Windows and macOS.  
> On Linux, install it with: `sudo apt-get install python3-tk`

### 3. Run the app

```bash
python travel_planner.py
```

---

## 🚀 Usage

### Generating an Itinerary

1. **Select a Destination** — Choose from 19 heritage cities in the dropdown
2. **Set Duration** — Pick 2, 3, 5, 7, or 10 days
3. **Choose Budget** — Budget / Mid / Luxury
4. **Pick Interests** — Toggle tags like History, Food, Photography etc.
5. **Select Travel Style** — Relaxed, Packed, Focused, or Flexible
6. **Choose Travellers** — Solo, Couple, Family, or Group
7. **Click "Generate AI Itinerary"** — Your plan appears on the right panel

### Exporting & Sharing

| Action | How |
|---|---|
| **Download PDF** | Click "Download PDF" → choose save location → opens automatically |
| **Share Link** | Click "Share Link" → HTML opens in browser → copy file path to share |
| **Save** | Click "Save" to bookmark (connect a database to persist) |

### VS Code Users
If you see Pylance warnings about `reportlab` imports, these are **not errors** — just missing type stubs. The app runs perfectly. To suppress:

```json
// .vscode/settings.json
{
  "python.analysis.diagnosticSeverityOverrides": {
    "reportMissingModuleSource": "none"
  }
}
```

---

## 📁 Project Structure

```
walk-through-history/
│
├── travel_planner.py          # Main application (single file)
│
├── README.md                  # Project documentation
│
└── requirements.txt           # Python dependencies
```

### Key Sections Inside `travel_planner.py`

```
travel_planner.py
│
├── COLOUR PALETTE             # UI colour constants
├── DESTINATION_DATA           # Full itinerary data for all cities
├── DESTINATIONS_LIST          # Dropdown city list
├── generate_pdf()             # ReportLab PDF builder
├── generate_share_html()      # Standalone HTML page generator
│
└── TravelPlannerApp (class)
    ├── _build_hero()          # Title / badge section
    ├── _build_form()          # Left panel: all input controls
    ├── _build_itinerary()     # Right panel: generated day cards
    ├── _build_slot()          # Individual morning/afternoon/evening slot
    ├── _download_pdf()        # PDF export handler
    └── _share_link()          # HTML share handler
```

---

## 📄 PDF Output

The exported PDF includes:

- **Header** — City name, tagline, and trip badges (days / budget / pace)
- **Stats Bar** — Total days, experiences, monuments, and estimated daily cost
- **Day Cards** — Each day with Morning (7 AM), Afternoon (1 PM), Evening (6 PM) slots
- **Activity Details** — Name, description, and interest tags per slot
- **Footer** — Generation timestamp

---

## 🌐 HTML Share Page

The share feature generates a **fully self-contained HTML file** with:

- The same dark gold visual theme as the app
- Responsive layout for mobile and desktop browsers
- All itinerary data embedded — no internet connection required
- Works offline and can be emailed or uploaded anywhere

---

## 🔧 requirements.txt

```
reportlab>=4.0.0
```

---

## 🤝 Contributing

Contributions are welcome! Here are some ideas to extend the project:

- [ ] Add real AI API integration (OpenAI / Claude) for dynamic itinerary generation
- [ ] Connect a SQLite database for saving/loading itineraries
- [ ] Add map integration showing monument locations
- [ ] Include hotel and restaurant recommendations per budget tier
- [ ] Add more destinations (international cities)
- [ ] Dark/light theme toggle
- [ ] Export to Google Calendar format

