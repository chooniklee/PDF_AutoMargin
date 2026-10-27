# 🎼 ScoreMargin Studio

A self-contained, browser-based web application for **semi-automatically cropping, deskewing, and standardizing margins of scanned sheet music PDFs**.

All processing runs 100% locally in your browser—no files are uploaded to any server.

## ✨ Key Features

- **Smart Score-Right-Edge Auto-Crop**:
  - Uses a 2D Integral Image local-density detector to find the exact ink bounding box while ignoring isolated scanner dust specks.
  - Detects the true right edge of the music staves (`scoreRight`) independently of corner page numbers, cropping every page at a uniform distance from the staff right edge.
  - Supports ignoring, including, or masking out old corner page numbers (`14`, `15`, etc.) and printing clean new page numbers.
- **Locked Horizontal Score Alignment Across Pages**:
  - When reformatting onto the target paper size (`Letter`, `A4`, `B4`, `Legal`), every page is horizontally anchored to `scoreRight` so the music staves stay at the exact same horizontal position from page to page—even when odd/even pages have alternating page numbers or system indentations.
  - Supports **Uniform Staff Scale** (keeps staff size consistent across all pages) and **Scale to Fit Margins**.
- **Interactive Crop Box & Deskew**:
  - Drag the 8 resize handles/edges to fine-tune individual margins, or drag inside the box to pan a fixed-size crop window.
  - Mouse wheel single-page navigation (`Wheel Up/Down` or `←/→` arrow keys).
  - **Auto-Deskew** using horizontal projection profile variance across staff lines, plus manual fine rotation (`-4°` to `+4°`).
- **Native 600 DPI Lossless & 1-Bit Monochrome Export**:
  - **⚡ Native 600 DPI Lossless (Default)**: Preserves the original PDF's native 600 DPI 1-bit `JBIG2` image streams, `/Rotate` tags, and `/CropBox` offsets via vector clipping and transformation matrices—resulting in zero quality loss and the same compact file size (~600 KB) as the original scan.
  - **🎯 600 / 300 DPI 1-Bit Monochrome**: Packs filtered pixels into true 1-bit `/DeviceGray /BitsPerComponent 1 /FlateDecode` streams when applying background cleanup or contrast boost.

## 🚀 Usage

1. **Online (GitHub Pages)**: Open `https://<your-username>.github.io/<repo-name>/`
2. **Offline (Local File)**: Double-click [`index.html`](index.html) or [`PDF_AutoMargin.html`](PDF_AutoMargin.html) to open directly in Chrome, Edge, or any modern browser.
