[README.md](https://github.com/user-attachments/files/34167358/README.md)
# 🏅 Olympic Games Analytics Dashboard (Power BI)

An interactive, six-page Power BI report that explores Olympic Games history: medals, countries, athletes, sports, host nations and participant demographics. Every page has an Olympic-themed background, consistent KPI cards and charts, and a page-navigation menu.

> **Status:** Design and layout work was done by editing the report definition (PBIR) directly. If you hit a problem opening a file, see [Troubleshooting](#troubleshooting).

---

## 📊 Report pages

| # | Page | What it answers |
|---|------|-----------------|
| 1 | **Global Medal Overview** | How many countries and medals overall? Who are the top 10 countries? How do gold, silver and bronze trend over the years, and how many events were held? |
| 2 | **Country Insights** | Pick a country (slicer) to see its athletes, total medals, medal efficiency, medal split by type, year-wise medal count and best sports. |
| 3 | **Athlete Spotlight** | Total athletes, top 10 athletes by medals, most-participated athletes, medal-winning vs total athletes, gender split and age distribution of medal winners. |
| 4 | **Sport & Event Analysis** | Pick a sport (slicer) to see medal trends over time, country dominance, athlete participation, top sports and events added per year. |
| 5 | **Host Country Analysis** | Which countries hosted most often, events conducted, host-country medal trend, and host vs non-host medal counts. |
| 6 | **Participant Demographics** | Youngest/oldest medal winners, male vs female athlete counts over time, participation by age group, gender-wise medal share and average age by year. |

---

## ✨ Features

- **Page navigation menu**: six buttons on every page with the current page highlighted (no bookmarks needed).
- **Olympic-themed backgrounds**: a unique background image per page.
- **Styled KPI cards and charts**: consistent fonts, titles, axis/label colors and a palette based on the five Olympic ring colors.
- **Gold / silver / bronze coding** on medal visuals.
- **Slicers** for country (page 2) and sport (page 4).
- Clear, descriptive visual titles on every chart.

---

## 🗂️ Repository contents

```
.
├── README.md
├── olympicgames_v2_main.pbix        # Final report, light theme + custom "Olympic Light" theme
├── olympicgames_v2_safe.pbix        # Same report without the custom theme file (fallback)
├── backgrounds_v2/                  # Backgrounds used by the v2 report (light + sidebar style)
├── backgrounds_v3/                  # Alternative standalone backgrounds (dark, illustrated scenes)
└── tools/                           # (optional) Python scripts used to generate the images / build the report
```

> Adjust the tree above to match what you actually commit.

---

## 🚀 Getting started

**Requirements:** Power BI Desktop (current release, Windows).

1. Clone or download this repository.
2. Open `olympicgames_v2_main.pbix` in Power BI Desktop.
3. If it will not open, try `olympicgames_v2_safe.pbix`.
4. Use the sidebar buttons to move between pages, and the slicers on pages 2 and 4 to filter.

### Using a different background

On any page: **Format → Canvas background → Image**, choose a file from `backgrounds_v2/` or `backgrounds_v3/`, set **Image fit = Fit** and **Transparency = 0%**.

The `backgrounds_v3/` set is dark, so use light chart text with it.

---

## 🎨 Design notes

- **Canvas:** 1920 × 1080 (16:9).
- **Layout:** left navigation sidebar (250 px), header band with page title, content area on a grid with 20 px gutters.
- **Palette:** Olympic ring colors (blue `#0085C7`, yellow `#F4C300`, black `#1A1A1A`, green `#009F3D`, red `#DF0024`) on a light canvas with a dark navy sidebar. Medals use gold `#D9A400`, silver `#9AA7B5`, bronze `#B8692B`.
- **Fonts:** Georgia for titles and KPI values; Segoe UI / Segoe UI Semibold for everything else.

---

## 🖼️ Background images

The backgrounds are **original illustrations generated with Python (Pillow / NumPy)**, not stock photos. They are included as JPEGs (1920 × 1080).

- `backgrounds_v2/` : light header scenes (podium and medal, globe, laurel and star, stadium track, skyline and fireworks, ribbons) with a navy sidebar.
- `backgrounds_v3/` : full-bleed dark scenes (medals on ribbons, bunting over a dotted world map, swimming pool, archery targets, stadium at dusk, crowd).

---

## 🛠️ How the report was produced

The report is stored in Power BI's **PBIR** (folder-based JSON) format. Styling, layout, navigation buttons and background images were applied by editing the report definition directly, then repackaging the `.pbix`:

- The data model (`DataModel`) is left **byte-for-byte unchanged**.
- `DataModel` must remain **stored (uncompressed)** inside the `.pbix` archive.
- The `SecurityBindings` file is **removed**. It acts as an integrity seal, and Power BI reports the file as corrupted if report files change while it is present. Power BI regenerates it on save.

---

## ⚠️ Troubleshooting

- **"Unable to open document / file is corrupted"**: use the `*_safe.pbix` file. If that also fails, open an issue and paste the text from *Copy details to clipboard* on the error dialog.
- **Slicer text looks dark or low-contrast**: set the font color under *Format → Values* (and *Header*).
- **Gold/silver/bronze colors not applied on the medal donut**: slice colors are matched by the values "Gold", "Silver" and "Bronze". If your data uses different labels, recolor under *Format → Slices*.
- **Backgrounds look cropped or stretched**: set *Image fit = Fit* and confirm the page size is 16:9.

---

## 📄 Data

Add your source here, for example:

- Dataset name and link: `…`
- Time period and coverage: `…`
- Refresh instructions: `…`

---

## ⚖️ Notes on trademarks and licensing

The Olympic rings and related emblems are trademarks of the International Olympic Committee (IOC). This project is an independent, non-commercial analytics/design exercise and is **not affiliated with or endorsed by the IOC**. Check the IOC's brand-usage rules before publishing the report publicly or using the imagery commercially.

The illustrations and scripts in this repository are released under the license of your choice (e.g. MIT). Add a `LICENSE` file.

---

## 👤 Author

Your Name · [GitHub]() · [LinkedIn](https://www.linkedin.com/in/your-profile)
