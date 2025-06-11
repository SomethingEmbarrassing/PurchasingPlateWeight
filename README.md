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
  download options for Excel, a plain PDF, or an annotated version of the
  original PDF showing the weight and price.

### Dependencies
- **pdf.js** – parses PDF files in the browser.
- **xlsx** – generates Excel files for download.
- **jsPDF** – creates the PDF export of the results.

### Current limitations
- OCR is provided via Tesseract.js but may be slow or inaccurate for complex
  scans.
- The script looks for the word `camber` near the top of each page and starts
  reading weights 1% of the page height below the `R` character. This approach
  skips the title region and adapts to slight layout changes.
- Page 1 has an additional rule that ignores text very close to the
  top margin (around y=768 on letter pages) to suppress header values.

### To do / planned improvements
- Allow configuring the cost multiplier.
- Support additional export formats such as CSV.
- Provide UI controls for adjusting parsing thresholds.
