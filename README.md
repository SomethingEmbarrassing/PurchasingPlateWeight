# PurchasingPlateWeight
Purchasing has been manually adding printed PDFs and multiplying for cost. HTML Doc to automate.

- OCR via Tesseract.js has been disabled. Run OCR externally if the PDF does
  not already contain selectable text.
## Running
1. Clone the repository or download the files.
2. Serve the directory with a local web server (e.g. `python -m http.server`).
   Then open `Purchasing Plate Weight V1.06.html` through that address.
   The HTML file loads **pdf.js**, **xlsx**, and **jsPDF** directly from CDNs so
   no extra installation is required.
3. Use the file picker or drag-and-drop area to load cut list PDFs. Simply
   clicking the drop zone will open the file dialog. Processing starts
   automatically once the PDF is selected or dropped. The script extracts the
   weight values, sums them and displays the total along with download options
   for Excel and PDF.


### Dependencies
- **pdf.js** – parses PDF files in the browser.
- **xlsx** – generates Excel files for download.
- **jsPDF** – creates the PDF export of the results.

### Current limitations
- OCR is provided via Tesseract.js but may be slow or inaccurate for complex
  scans.

- Parsing relies on finding the "Camber" column header to start reading the
  weight values from the rightmost column. Once the header is found the script
  continues reading values on all subsequent pages. If the anchor text is
  missing or spelled differently the results may be incorrect.


### To do / planned improvements

- Allow configuring the cost multiplier. (check if this is already implemented)
- Add an input area where the user can specify a PO number. (check if this is already implemented)
- Place the total weight, dollar value and the entered PO number onto the
  generated PDF before returning it to the user.
- Provide UI controls for adjusting parsing thresholds.


