# 3MF Compare Tool

A free, browser-based tool to compare two `.3mf` files and see exactly which slicer settings differ — instantly, with no uploads.

Built for BambuStudio and OrcaSlicer, but also works with other PrusaSlicer-based slicers (Elegoo, Orca forks, etc.).

---

## Features

- Compare two `.3mf` files side by side
- Highlight only the settings that actually differ
- View full settings or differences only
- Search and filter settings instantly
- Copy differences as a clean Markdown table (perfect for forums/Reddit)
- Dedicated views for:
  - All settings differences
  - Printer & profile summary
  - Filament settings
- Color preview for filament colors
- Handles slicer quirks (arrays, duplicated values, etc.)
- No install required — runs directly in your browser

---

## Privacy

- 100% local processing — your files never leave your device
- No uploads, no tracking, no data collection
- Uses JSZip (via CDN with integrity check) to read `.3mf` files safely

---

## How It Works

A `.3mf` file is essentially a ZIP archive.

Inside each file:
- `Metadata/project_settings.config` contains all slicer settings (JSON)

This tool:
1. Opens both `.3mf` files locally
2. Extracts the settings JSON
3. Normalizes values to avoid false differences
4. Displays only what actually changed

---

## Usage

1. Open the tool in your browser
2. Drop in:
   - File A
   - File B
3. Click **Compare Files**
4. Explore:
   - Settings Differences
   - Printer & Profile
   - Filaments
5. (Optional) Copy results as Markdown

---

## Example Output

```
| Setting | File A | File B |
|:---|:---|:---|
| layer_height | 0.2 | 0.16 |
| infill_density | 15 | 25 |
```

---

## Why This Exists

Slicers don’t provide a real "diff" view.

When troubleshooting prints or sharing profiles, it’s hard to know:
- What actually changed
- What caused a print issue
- What someone else did differently

This tool solves that.

---

## Supported Slicers

- BambuStudio
- OrcaSlicer
- PrusaSlicer-based slicers (partial support depending on keys)

Note: Some slicers may use different setting names.

---

## Limitations

- Requires `project_settings.config` to exist in the `.3mf`
- Differences depend on how slicers store values internally
- Some advanced/custom keys may not appear in grouped views

---

## Tech Stack

- Vanilla JavaScript (no framework)
- JSZip (for reading `.3mf` files)
- Fully client-side

---

## Contributing

Feel free to:
- Open issues
- Suggest features
- Submit improvements

---

## License

MIT license. 

