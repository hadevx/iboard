# 🎨 Whiteboard

An interactive, browser-based whiteboard application inspired by Excalidraw and Eraser. Built with **React** and the **HTML5 Canvas API** — no heavy drawing libraries, just raw canvas power.

---

## ✨ Features

- 🖼️ **Image Uploads** — drag and drop or upload images directly onto the canvas
- 🗒️ **Sticky Notes** — add, move, edit, and delete colorful sticky notes
- 🧹 **Eraser Tool** — precisely erase parts of your drawing
- ↩️ **Undo / Redo** — full history stack with keyboard shortcuts
- 📤 **Export** — save your board as PNG or SVG
- 🖱️ **Pan & Zoom** — navigate large canvases with ease
- 🎨 **Infinite Canvas** — no limits on your workspace

---

## 🚀 Getting Started

### Prerequisites

- Node.js v18+

### Installation

```bash
# Clone the repository
git clone https://github.com/your-username/whiteboard.git
cd whiteboard

# Install dependencies
npm install

# Start the development server
npm run dev
```

Open `http://localhost:5173` in your browser.

### Build for Production

```bash
npm run build
npm run preview
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Framework | React |
| Drawing Engine | HTML5 Canvas API |
| Build Tool | Vite |
| Styling | CSS / Tailwind CSS |

---

## 📁 Project Structure

```
├── src/
│   ├── components/
│   │   ├── Canvas.jsx          # Main drawing canvas
│   │   ├── Toolbar.jsx         # Tool selection sidebar
│   │   ├── StickyNote.jsx      # Sticky note component
│   │   └── ExportMenu.jsx      # PNG / SVG export
│   ├── hooks/
│   │   ├── useCanvas.js        # Canvas drawing logic
│   │   ├── useHistory.js       # Undo / redo stack
│   │   └── useExport.js        # Export helpers
│   ├── utils/
│   │   ├── draw.js             # Drawing primitives
│   │   └── export.js           # Canvas → PNG / SVG conversion
│   ├── App.jsx
│   └── main.jsx
├── public/
├── index.html
└── vite.config.js
```

---

## 🎮 Tools & Shortcuts

### Toolbar

| Tool | Description |
|---|---|
| ✏️ Draw | Freehand drawing on the canvas |
| 🧹 Eraser | Erase parts of your drawing |
| 🗒️ Sticky Note | Add a draggable sticky note |
| 🖼️ Image | Upload an image onto the board |
| 🤚 Pan | Pan around the canvas |

### Keyboard Shortcuts

| Shortcut | Action |
|---|---|
| `Ctrl + Z` | Undo |
| `Ctrl + Y` / `Ctrl + Shift + Z` | Redo |
| `Ctrl + S` | Export as PNG |
| `Space + Drag` | Pan canvas |
| `Scroll` | Zoom in / out |
| `Delete` | Delete selected element |

---

## 🖼️ How It Works

### Drawing Engine

All drawing is handled directly on an HTML5 `<canvas>` element using the 2D context API. Each stroke, image, and element is stored as a data structure in a history stack, which enables undo/redo without re-rendering the entire React tree.

```
User Input (mouse / touch)
        │
        ▼
Canvas event handlers (onMouseDown, onMouseMove, onMouseUp)
        │
        ▼
Draw to canvas context (ctx.beginPath, ctx.stroke, etc.)
        │
        ▼
Push to history stack → enables Undo / Redo
```

### Undo / Redo Stack

History is maintained as an array of canvas snapshots (`ImageData`). Each action pushes a new snapshot; undo/redo navigates the stack and restores the corresponding state.

### Export

- **PNG** — uses `canvas.toDataURL("image/png")` and triggers a file download
- **SVG** — reconstructs the canvas elements as SVG markup and exports as `.svg`

---

## 📤 Export

Click the **Export** button in the toolbar:
- Choose **PNG** for a raster image (best for sharing)
- Choose **SVG** for a scalable vector file (best for editing)

---

## 📄 License

This project is licensed under the MIT License.
