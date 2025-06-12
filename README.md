# PurchasingPlateWeight
Purchasing has been manually adding printed PDFs and multiplying for cost. HTML Doc to automate.

Main function of this script is to extract weight of steel plates from cut list, sum weights, multiply by 0.95 and display cost.

## Running
1. Clone the repository or download the files.
2. Serve the directory with a local web server (e.g. `python -m http.server`).
   Then open `Purchasing Plate Weight V1.06.html` through that address.
   The HTML file loads **pdf.js**, **xlsx**, and **jsPDF** directly from CDNs so
   no extra installation is required.
3. Use the file picker or drag-and-drop area to load cut list PDFs. The script
   extracts the weight values, sums them and displays the total along with
   download options for Excel and PDF.

### Dependencies
- **pdf.js** – parses PDF files in the browser.
- **xlsx** – generates Excel files for download.
- **jsPDF** – creates the PDF export of the results.

### Current limitations
- OCR is provided via Tesseract.js but may be slow or inaccurate for complex
  scans.
- Parsing relies on finding the "Camber" column header to start reading the
  weight values from the rightmost column. If that anchor is missing or spelled
  differently the results may be incorrect.

### To do / planned improvements
- Allow configuring the cost multiplier.
- Add an input area where the user can specify a PO number.
- Place the total weight, dollar value and the entered PO number onto the
  generated PDF before returning it to the user.
