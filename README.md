# Privacy-First WhatsApp Export Chat Viewer & Analyzer

A complete, polished, responsive personal **WhatsApp exported-chat viewer and analyzer** static web application.

> **Privacy Statement**: This application is designed to process WhatsApp exports locally inside your browser memory. Your chat content is not intentionally transmitted to any server, database, or third-party service.

---

## 🌟 Key Features

- **100% Local & Offline First**: Zero backend, zero database, zero server API calls, zero analytics, zero telemetry.
- **ZIP & Attachment Support**: Supports both `.txt` (`_chat.txt`) and `.zip` archives containing images, videos, audio, and documents extracted 100% locally via bundled JSZip.
- **Multi-Format Modular Parser**:
  - Android style: `3/15/24, 2:30 PM - John: Hello`
  - iOS bracketed format: `[3/15/24, 2:30:18 PM] John: Hello`
  - ISO date format: `[2024-03-15, 14:30:18] John: Hello`
  - European format: `15/03/2024, 14:30 - John: Hello`
  - Dotted format: `15.03.2024, 14:30 - John: Hello`
  - Non-breaking spaces (`\u202f`, `\u00a0`), 12h/24h time formats.
- **High-Performance Virtual Scrolling**: Render 260,000+ messages seamlessly with smooth sub-60fps scrolling and low memory footprint.
- **XSS & Security**: Strict HTML sanitization and URL detection with `target="_blank" rel="noopener noreferrer"`.
- **Search & Multi-Filtering**: Instant debounced search with prev/next navigation, highlighting, participant filtering, message type filtering, and date range filtering.
- **Statistics & Analytics Dashboard**: Overview metrics, participant rankings, visual SVG/CSS activity charts (day of week, hour of day, monthly timeline), stop-word filtered word frequency, emoji leaderboard, media statistics, and conversation insights.
- **Timeline Tree & Jump to Date**: Accordion tree navigation for Years/Months and jump-to-date selector.
- **Export Capabilities**: Generate `.txt`, `.json`, and `.csv` files locally, or use `@media print` layout for PDF export.
- **Automated Test Suite**: Built-in 25-scenario browser parser test runner.

---

## 📱 How to Export Your WhatsApp Chat

### Android
1. Open the chat in WhatsApp.
2. Tap the **three dots menu (⋮)** → **More** → **Export chat**.
3. Select **Without media** (for `.txt`) or **Include media** (for `.zip`).
4. Save the `.txt` or `.zip` file to your device.

### iOS (iPhone)
1. Open the chat in WhatsApp.
2. Tap the contact or group name at the top.
3. Scroll down and tap **Export Chat**.
4. Choose **Without Media** or **Attach Media**.
5. Save the `.zip` file to Files or your local storage.

---

## 🚀 Running Locally

Because this project uses plain HTML5, CSS3, and native ES modules, you can serve it with any local static web server or open it directly in a modern web browser.

### Using Python
```bash
python -m http.server 8000
```
Then open `http://localhost:8000` in your browser.

### Using Node.js `npx http-server` or `serve`
```bash
npx http-server .
```

---

## 🌐 Deploying to GitHub Pages

1. Push this repository to GitHub.
2. Go to **Settings** → **Pages**.
3. Under **Source**, select `main` branch and `/ (root)` folder.
4. Click **Save**.

The site will automatically deploy to:
`https://<your-username>.github.io/<repository-name>/`

All file paths are relative, ensuring seamless deployment on GitHub Pages subpaths.

---

## 🔒 Security & Privacy Model

- **Local Memory Processing**: Files selected via Drag & Drop or file picker are read using `FileReader` and processed in-memory.
- **No Remote Network Requests**: The app requires no internet access once loaded.
- **Sanitized Rendering**: Untrusted chat text is escaped before rendering formatting rules (`*bold*`, `_italic_`, `~strikethrough~`).

---

## 🛠️ Diagnostics & Parser Reporting

If you encounter an unrecognized line or custom format:
1. Click the **🛠️ Diagnostics** button in the top navigation bar.
2. Inspect line counts, system entries, media counts, and unrecognized line previews.
3. Run the built-in **🧪 25-Test Parser Suite** to verify parser integrity.
