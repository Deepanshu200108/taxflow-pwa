# TaxFlow v9 — classic plain invoice layout

## Publish/update
Replace the files in the root of your existing GitHub Pages repository with these files. Keep the repository public app files only; never upload customer invoices, backups or private financial data.

## Install
Open the GitHub Pages HTTPS URL in Microsoft Edge → menu → Apps → Install this site as an app.

## Feedback implemented
- Invoice number suggestion: focus the invoice number field or press Tab while it is blank / contains only the prefix. It suggests the next sequence using the configured prefix. Default is `JAI/26-27/27`, based on the latest invoice number visible in the uploaded workbook (`JAI/26-27/26`). Change prefix and next sequence in Settings.
- Customer autocomplete, with sample customers extracted from the uploaded workbook.
- Service description and SAC autocomplete, with common service examples from the workbook.
- Customer billing/registered address and project work/site address are separate fields.
- Company name, Jaipur registered address, GSTIN `08APRPD1249Q1ZA`, PAN `APRPD1249Q`, and state code `08` are prefilled from the workbook and editable in Settings.
- Invoice line columns follow the requested layout: Sr. No., Description of Services, HSN/SAC, GST Rate, Quantity in MT, Rate, Amount.
- Invoice PDF includes company details, buyer billing address, separate work/site address, buyer GSTIN, work order and service line table.

## Local data and PDFs
Records are stored in this browser profile's IndexedDB. Select a folder from Settings to write PDF copies into `Invoices` and `RA Bills` folders. Browser folder access requires explicit permission and desktop Edge/Chrome. If folder access is unavailable, download PDFs from the in-app preview.

## Moving to another laptop
Use JSON export/import for invoice/RA records, customers, services and company settings. This JSON backup does not embed PDF binary files. Copy the separate `Invoices` and `RA Bills` folders too. No automatic cloud synchronization is included.

## Important limitations
This is a prototype, not certified GST/accounting software. GST calculations are simplified and manual intra/inter-state selection is provided. The app does not determine place of supply, validate GST law, support IRN/e-invoice, e-way bills, credit/debit notes, cancellation workflow or audit logs. Confirm SAC, rates, GST treatment, TDS, labour cess and place-of-supply with your CA before statutory use. Some historical Excel invoices have inconsistent formulas/tax labels; these have not been copied as calculation rules.


## v6 invoice layout update
- Reworked A4 PDF invoice layout with company masthead, buyer and project/site address blocks, work order metadata, styled service table, tax summary, bank details and declaration/signature area.
- Company identity is stored once in Settings and reused on each PDF. Customer master selection fills saved buyer details; project site remains invoice-specific.
- Confirm all company bank/GST details and statutory invoice fields before real issue.

## v7 fixes: simpler entry and reliable local PDF download
- Removed company-state, default GST and bank-detail entry from the invoice form. Company identity and bank details are read from Settings.
- Customer selection now fills GSTIN, billing address, work-site address and state code from the customer master. Only edit fields that are new for this bill.
- Corrected service-line field mapping so description, SAC, GST rate, quantity, rate and amount are saved in the right columns.
- On every successful save, TaxFlow archives the PDF in this browser's IndexedDB and automatically downloads a named PDF into the browser's Downloads folder.
- Optional archive-folder copy remains available in Settings. If folder permission is unsupported or denied, the automatic Downloads copy still works.
- Updated the service-worker cache version so GitHub Pages clients fetch the new interface after refresh.

**Note:** PDF generation uses jsPDF from a CDN, so the first PDF generation requires an internet connection. After the app has loaded and the library is cached by the browser, availability may improve offline, but do not rely on offline PDF generation until tested.


## v9 classic invoice layout
- Removed the colored masthead, colored invoice-number panel, rounded cards and decorative styling from the PDF. No logo is included.
- Uses a plain white A4 page, black typography, restrained grey rules, simple table headings and aligned totals for a traditional business invoice.
- Invoice number is placed on the same line as the TAX INVOICE heading. Work order number and date remain clearly visible near the top.
- Service table, buyer GSTIN, billing/site addresses, bank details and declaration are retained.
- Corrected round-off presentation: only a non-zero round-off line is shown, and the total remains the exact saved invoice total.
- Service worker cache updated to v9 so deployed clients can load the revised PDF code.
