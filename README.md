# 🗺️ PhotoMap — Local Photo & Video Map

> **Explore your local photos and videos on an interactive geographic map, just like Google Photos.**  
> 100% private, offline, ultra-fast, and powered by lightweight JSON indexing.

---

## ✨ Features

- 📍 **Interactive Geographic Map**: Explore all your photos and videos mapped by their GPS coordinates.
- ⚡ **Lightweight JSON Caching (`photomap_index.json`)**: Automatically saves an index inside your photos folder. Reopening large collections (10,000+ photos) loads in **< 100 milliseconds**.
- 💾 **Dual-Layer Persistence**: Caches metadata to both `photomap_index.json` and browser **IndexedDB** for instant reloads.
- 🚀 **High-Performance Architecture**: Lazy file resolution and in-memory URL caching prevent tab crashes while keeping thousands of thumbnails instantly accessible in memory without re-fetching from disk.
- 🔍 **Cluster & Heatmap Views**:
  - Marker clusters with count indicators.
  - Heatmap mode to visualize travel hotspots and location density.
  - Bottom location drawer to browse all photos taken in a specific area or cluster.
- 📅 **Timeline & Media Filtering**: Filter photos and videos by year or switch between photo and video modes.
- 🖼️ **Full-Screen Lightbox**: High-resolution viewer with EXIF metadata (date taken, GPS coordinates, file size) and a quick shortcut to open locations in Google Maps.
- 🔒 **100% Offline & Private**: No data or photos are uploaded to any server. Everything runs directly inside your local browser.
- 📦 **Google Photos Takeout Friendly**: Recursively scans flat or deeply nested folders (e.g. `Year/Month` takeout folder structures).

---

## 🚀 Getting Started

### 1. Requirements
- A Chromium-based browser supporting the **File System Access API**:
  - **Google Chrome** (Recommended)
  - **Microsoft Edge**
  - **Brave Browser**
  - **Opera**

### 2. How to Use
1. Double-click or open [`index.html`](file:///run/media/samito/5D11692847991CD8/New%20folder/index.html) in your browser.
2. Click **"Select Photos Folder"** and choose any directory containing your photos or Google Takeout archive.
3. PhotoMap will scan the metadata (EXIF GPS & dates) and instantly display your memories on the map.
4. An index file (`photomap_index.json`) will be generated so future opens of the same folder load instantaneously!

---

## 📂 Supported Formats

| Media Type | Supported Extensions |
| :--- | :--- |
| **Photos** | `.jpg`, `.jpeg`, `.png`, `.webp`, `.heic`, `.heif`, `.avif`, `.gif`, `.bmp`, `.tiff` |
| **Videos** | `.mp4`, `.mov`, `.mkv`, `.avi`, `.webm`, `.m4v`, `.3gp` |

---

## ⚙️ Navigation & Controls

| Control | Description |
| :--- | :--- |
| `🗺️ Map` | View photo markers, clusters, and heatmaps on the world map. |
| `🖼️ All Photos` | Browse your entire library in a virtualized grid view. |
| `📅 Year Dropdown` | Filter media taken in a specific year. |
| `📷 / 🎥 Dropdown` | Filter between all media, photos only, or videos only. |
| `⚡ Re-scan` | Force a fresh re-scan of the folder if you added new media. |
| `⚙️ Options` | Export or import `.json` metadata indexes. |
| `🌍 Reset View` | Re-center map to fit all mapped photo markers. |
| `🔥 Heatmap` | Toggle heatmap density overlay on and off. |

---

## 🛠️ Tech Stack

- **Vanilla HTML5 & CSS3**: Custom glassmorphism dark theme with Plus Jakarta Sans typography.
- **Vanilla JavaScript (ES6+)**: Zero framework dependencies, pure asynchronous File System Access API.
- **[Leaflet.js](https://leafletjs.com/)**: Interactive map engine with CartoDB Voyager tiles.
- **[Leaflet.markercluster](https://github.com/Leaflet/Leaflet.markercluster)**: Dynamic marker clustering.
- **[Leaflet.heat](https://github.com/Leaflet/Leaflet.heat)**: Heatmap visualization layer.
- **[exifr](https://github.com/MikeKovarik/exifr)**: Fast EXIF and GPS parser.

---

## 🔒 Privacy

PhotoMap does **NOT** collect telemetry or upload photos anywhere. All file reads, EXIF extractions, and rendering happen strictly within your local browser sandbox.
