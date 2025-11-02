## JASS & Media File Generator (Single-page HTML)

This is a single-page HTML application (no-server) designed to generate JASS code (for Warcraft III) and package related media files into a .zip file with a specific structure.

## Overview

- Manage 3 independent entries: `Login - 1`, `Login - 2`, `Login - 3`.
- Each entry contains a `Name` tab (text color/gradient editing, JASS color format output) and `Image/Sound` tab (media upload, validation, preview).
- Multi-language support (6 languages): English (default), Việt Nam, Indonesia, Russia, Thailand, Korean.
- Clicking `Save` (after entering a `Primary Name` at the top) generates and downloads a .zip file with the structure described below.

## Key Features

1. Manage 3 independent Logins (separate text & file data).
2. `Name` Tab:
   - Simple rich-text-like editor with color formatting:
     - Color 1 / Color 2 (solid colors)
     - Create Gradient (two-color gradient on selection)
   - Converts colored text to JASS color codes: format `|cffRRGGBB...|r`.
   - Output limit after formatting: maximum 100 characters per `Name`.
3. `Image/Sound` Tab:
   - Images: accepts `.png` or `.jpg`/`.jpeg`.
   - Automatic validation:
     - 16:9 aspect ratio check.
     - Maximum dimensions: 1920 x 1080 (px).
   - Converts images to `.tga` (24-bit RLE) before packaging.
   - Audio: accepts `.mp3`, `.wav` (and other common formats). Checks that audio duration does not exceed 30 seconds.
   - Preview functionality for both images and audio before export.
4. `.zip` Export:
   - Users must enter a `Primary Name` (required). This name is used for the zip file (e.g., `MyName.zip`).
   - The zip contains a `Name.txt` file with generated JASS code and a `Title/` folder with renamed and converted media files.

## ZIP File Structure (Export)
```
MyName.zip/
|
|-- Name.txt
|
|-- Title/
|   |-- MyName1.tga
|   |-- MyName1.mp3
|   |-- MyName2.tga
|   |-- MyName3.mp3
|   |-- ...
```
- `Name.txt`: Auto-generated JASS code from the 3 Logins' input data.
- `Title/`: Contains converted media files (images -> `.tga`) with the `Primary Name` prefix.

## Quick Start Guide

1. Open `index.html` in a modern browser (Chrome/Edge/Firefox). The app runs entirely client-side, no server needed.
2. (Optional) Select your preferred language from the dropdown.
3. Enter a `Primary Name` at the top—this will be your zip filename and media prefix.
4. Select `Login - 1` (or 2/3) to edit content:
   - `Name` tab: enter text, select areas and apply `Color 1`/`Color 2` or `Create Gradient`. Check length (max 100 characters after formatting).
   - `Image/Sound` tab: upload images (.png/.jpg) and/or audio (.mp3). Preview files after upload.
5. Repeat for `Login - 2` and `Login - 3` if needed.
6. Click `Save` at the bottom (left panel). The browser will download your .zip file.

## File Validation & Notes

- Images:
  - Only accepts `.png`, `.jpg`/`.jpeg`.
  - 16:9 aspect ratio required. Non-compliant images must be adjusted before upload.
  - Maximum size: 1920 x 1080 px. Larger images will be rejected.
  - Images are converted to `.tga` 24-bit RLE before packaging.
- Audio:
  - Maximum duration: 30 seconds. Longer files will be rejected.
  - Only `.mp3` format is supported.

## Quick Use 

Open `index.html` directly (default browser):

## Media Processing Tips

- For non-16:9 or oversized images, use an image editor (Photoshop, GIMP, or online tools) to crop/resample to 16:9 and <=1920x1080.
- For audio over 30s, trim using Audacity or any audio editor.

## Important Limitations

- Each `Name` entry's formatted output (after JASS color coding) cannot exceed 100 characters. The application will prevent export if this limit is exceeded.

## Language Support

- Interface supports: English (default), Việt Nam, Indonesia, Russia, Thailand, Korean.
- Switch languages anytime through the interface dropdown.

## Technical Notes

- The application runs entirely client-side (browser). Image conversion to `.tga` and zip packaging are handled by JavaScript libraries (if implemented in the code). Use a modern browser for best performance.

## Troubleshooting

- If .zip download fails: check browser console for errors (file too large, conversion error, or missing `Primary Name`).
- If media preview doesn't show: verify file readability or try a different file to isolate the issue.

## License

This documentation and accompanying examples come with no specific license; consider adding an MIT license to your repo if you plan to use the source code.

## Contact

Need additional README content (implementation details, advanced usage) or have questions? Feel free to request updates.

---

This file was automatically generated to help you quickly understand the `JASS & Media File Generator`.
