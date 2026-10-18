# ZEN-PKG-Printing — Master Carton Label Generator

A single-page web app that generates print-ready **master carton label** images (PNG, 300 DPI) from a few inputs.

**Use it here:** https://melvinhtet.github.io/ZEN-PKG-Printing/

## Label types

| Type | Inputs | Output size |
|------|--------|-------------|
| **Trade packing** | Product Number, Quantity, ITF-14 code | 8 × 4 in (2400 × 1200 px) |
| **Bulk packing** | Product Number (`XXXXX-XXXXX`), Quantity, Selectivity number (`HP 937`) | 6 × 4.5 in (1800 × 1350 px) |
| **Host packing** | Product Number (`XXXX-XXXX`), Quantity | 6 × 4.5 in (1800 × 1350 px) |

## What it generates

- Code 128 barcodes for 1P (product number), Q (quantity), 1S (processing date), 1T (traceability ID), 4L (country of origin) and warranty codes
- Code 39 quantity barcode on bulk labels
- Data Matrix with the full traceability string
- ITF-14 with bearer bars (trade labels) — the check digit is verified, or added automatically when you enter 13 digits
- The **(30P) OPTION** line is printed only when the product number contains `#`

Advanced settings (processing date/time, country of origin, warranty in months, optional logo) are auto-filled and can be changed under **Advanced**. The site prefix in the Data Matrix / 1T code is set by the label type (S60 for trade and bulk, K80 for host).

## How to use

1. Open the link above in any modern browser (Chrome or Edge recommended).
2. Choose **Trade packing**, **Bulk packing** or **Host packing**.
3. Fill in the inputs — the preview updates live and flags any input errors.
4. Click **Download PNG** or **Copy image** and paste it into your label software.

No installation and no server: everything runs in the browser. Barcodes are rendered with [bwip-js](https://github.com/metafloor/bwip-js).

## Running offline

Download `index.html` and open it directly. An internet connection is still needed the first time to load the barcode library and fonts.
