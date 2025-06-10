# PurchasingPlateWeight
Purchasing has been manually adding printed PDFs and multiplying for cost. HTML Doc to automate.

Main function of this script is to extract weight of steel plates from cut list, sum weights, multiply by 0.95 and display cost.

## Running
1. Clone the repository or download the files.
2. Serve the directory with a local web server (e.g. `python -m http.server`).
   Then open `Purchasing Plate Weight V1.05.html` through that address.
   The HTML file loads **pdf.js**, **xlsx**, and **jsPDF** directly from CDNs so
   no extra installation is required.
3. Drag and drop cut list PDFs onto the page (or use the file picker). The
   script will extract the weight values, sum them and display the total along
   with download options for Excel and PDF.

### Dependencies
- **pdf.js** – parses PDF files in the browser.
- **xlsx** – generates Excel files for download.
- **jsPDF** – creates the PDF export of the results.

### Current limitations
- Only the first page of the PDF is processed.
- Drag-and-drop upload is not yet implemented; use the file picker.
- No OCR support, so scanned PDFs cannot be read.

### To do / planned improvements
- Add OCR functionality within the HTML script.
- Make sure drag and drop of PDFs is functional.
- Handle multi-page PDFs and other enhancements.
- Brainstorm improvement ideas.
