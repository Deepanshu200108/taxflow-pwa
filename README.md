# TaxFlow v5 — invoice autocomplete and workbook layout update

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
