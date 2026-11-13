# TaxFlow v3 — WebView-style PWA

This package is a browser-installed desktop-style PWA. It does not require Python, Node, Streamlit, or a Windows EXE on the destination laptop.

## Important architecture
- Static HTML/CSS/JavaScript; no backend or server-side database.
- Records are stored in IndexedDB in the browser profile on that laptop.
- PDFs are generated using the browser's Print dialog: choose **Save as PDF**.
- Records do NOT sync between laptops. Export a JSON backup from Invoice Register and keep PDF files backed up.
- Host the folder on an HTTPS static host (for example GitHub Pages) to enable PWA installation and service-worker offline caching. The code and UI are hosted; invoice records remain in the browser's local IndexedDB.

## Publish using GitHub Pages
1. Create a private GitHub repository named `taxflow-pwa`.
2. Upload all files in this folder to the repository root.
3. In repository Settings → Pages, choose Deploy from a branch → `main` → `/ (root)` → Save.
4. Wait for the HTTPS Pages URL to appear.
5. Open that URL in Microsoft Edge on each laptop.
6. Edge menu (…) → Apps → Install this site as an app. Pin it to Start or create a desktop shortcut.

GitHub Pages hosting may be public depending on your GitHub plan/repository configuration. Do not put customer records, GSTINs, PDFs, or other private data in the repository.

## Local use / install
The PWA must first be served from HTTPS or localhost for service-worker installation. Opening index.html as a file will let you test the UI, but installation/offline PWA features will not work correctly.

## Data safety
Use Invoice Register → Export backup JSON regularly. Browser storage is local to the browser profile and can be cleared by browser cleanup, profile reset, or uninstall/data deletion. Keep downloaded PDFs in Documents/TaxFlow yourself.

## Limitations in this starter
- This is a functional prototype, not certified GST software.
- SAC is currently a placeholder in the preview; verify and add correct SAC per service.
- Invoice amount in words, HSN/SAC master, credit/debit notes, cancellation, audit trail, import/restore, and e-invoicing/IRN are not implemented.
- GST is simplified to an entered rate and an intra/inter-state toggle. Confirm place-of-supply, rates, reverse charge, TDS and cess with your CA.
- The PDF preview uses browser print-to-PDF rather than silently writing to a protected folder. Browsers do not permit arbitrary silent writes to local folders without explicit user permission.
- Data is not shared across laptops. Export/import workflow is needed for migration.
