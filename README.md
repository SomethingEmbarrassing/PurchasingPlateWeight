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
- The script skips tokens near the top of the page to avoid title block
  numbers. The comparison uses `0.85` (meaning 85% of the page height) to
  exclude the top 15% of the page. Adjust this threshold in the HTML if your
  layout differs.
- Page 1 has an additional rule that ignores text very close to the
  top margin (around y=768 on letter pages) to suppress header values.

### To do / planned improvements
- Allow configuring the cost multiplier.
- Support additional export formats such as CSV.
- Provide UI controls for adjusting parsing thresholds.
