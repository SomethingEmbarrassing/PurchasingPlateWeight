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

3. Use the file picker or drag-and-drop area to load cut list PDFs. The script

  extracts the weight values by grabbing the last numeric token from each line
  of the rightmost column. It sums these weights and displays the total along
  with download options for Excel, a plain PDF, or an annotated version of the
  original PDF. The annotated export writes the PO number, total weight and
  estimated cost onto the first page so the summary travels with the document.


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
- Support additional export formats such as CSV.
- Provide UI controls for adjusting parsing thresholds.

