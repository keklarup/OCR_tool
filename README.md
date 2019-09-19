# OCR_tool
Notebooks demoing extracting text from PDFs using GhostScript and Tesseract. A few blank example PDFs are included in the repository as well.

### Pipelines:

#### Full page OCR:
1. Given pdf, convert into images with ghostscript
2. Given an image, extract text using Tesseract.
3. (Optional) Identify desired data from extracted text using bookend instruction language.

#### Cell based OCR:
1. Given pdf, convert into images with ghostscript
2. Given an image, identify long horizontal and vertical lines.
3. Split image into many subimages (cells) based on the found horizontal and vertical lines.
4. OCR each cell.
5. Combine results in csv.

### Tools:
* ghostscript -- to convert pdfs to images so that they can be OCR'd.
* tesseract -- to extract text from images
* python -- glue to run ghostscript, tesseract, perform image manipulations, and compile results

#### The main features of this notebook (converting PDFs to PNGs and OCRing PNGs to extract text) are not done by Python. They are being done by command line tools GhostScript and Tesseract. Those need to be installed before this notebook will do anything.

Starter places for easy installs of those tools:
1. Tesseract: https://github.com/UB-Mannheim/tesseract/wiki -- A full installer for Windows. But hosted outside the US. Domestic installers for older versions of Tesseract may be found here: https://github.com/tesseract-ocr/tesseract/wiki/4.0-with-LSTM#400-alpha-for-windows

2. Ghostscript: https://www.ghostscript.com/download/gsdnld.html

#### Ghostscript and Tesseract where both installed on a Windows 10 laptop when creating this demo. The tools were installed in subfolders of this projects folder. When being called by the Python OS package in the code below, the relative filepath is being given to the executable application files. 
