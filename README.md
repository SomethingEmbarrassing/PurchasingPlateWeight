# PurchasingPlateWeight
Purchasing has been manually adding printed PDFs and multiplying for cost. HTML Doc to automate.

Main function of this script is to extract weight of steel plates from cut list, sum weights, multiply by 0.95 and display cost.

## Running
1. Clone the repository or download the files.
2. Serve the directory with a local web server (e.g. `python -m http.server`).
   Then open `Purchasing Plate Weight V1.05.html` through that address.
   The HTML file loads **pdf.js**, **xlsx**, and **jsPDF** directly from CDNs so
   no extra installation is required.
3. Use the file picker to select cut list PDFs. Drag-and-drop support is
   planned but not yet implemented. The script will extract the weight values,
   sum them and display the total along with download options for Excel and
   PDF.

### Dependencies
- **pdf.js** – parses PDF files in the browser.
- **xlsx** – generates Excel files for download.
- **jsPDF** – creates the PDF export of the results.

### Current limitations
- Drag-and-drop upload is still pending; use the file picker for now.
- No OCR support, so scanned PDFs cannot be read.
- The script skips tokens near the top of the page to avoid title block
  numbers. Adjust the `0.15` Y-threshold in the HTML if your layout
  differs.
- Page 1 has an additional rule that ignores text very close to the
  top margin (around y=768 on letter pages) to suppress header values.

### To do / planned improvements
- Add OCR functionality within the HTML script.
- Make sure drag and drop of PDFs is functional.
- Handle multi-page PDFs and other enhancements.
- Brainstorm improvement ideas.
