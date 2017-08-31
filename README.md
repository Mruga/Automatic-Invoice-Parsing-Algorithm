# Automatic Invoice Parser Algorithm

The main aim to developer this algorithm is to help companies that processes invoice manually, try to convert this manual process to automation which can help reduce the manual labour.
The algorithm will be performing the following:
•	Using the template match the PDF files
•	Extract text from pdf
•	Search for regular expression in the result
•	Save result as csv.
•	Define currency in template
Starting from the PDF files the output displays
{'issuer': 'WM-RECYCLE AMERICA L.L.C.', 'amount': 8400.13, 'date': datetime.datetime(2016, 7, 28, 0, 0), 'invoice_number': '21529V-01', 'currency': 'USD', 'desc': 'Invoice 21529V-01 from WM-RECYCLE AMERICA L.L.C.'}
Installation
Following python libraries that needs to be installed:
•	pdfminer 
•	tesseract
•	pytessarct
•	pyocr
•	yaml
•	PIL (Python Imaging Library)
Template System
Templates used in this algorithm are based on Yaml. The template defines keywords to match the right template and regular expression for the fields to be extracted.
How the template has been created?
Basically, a template system defines which attributes to retrieve from invoice. Each template should work on all invoices of company or subsidiary company.
Simple Invoice Template:
issuer: Client name
fields:
  amount: regular expression
  date: regular expression
  invoice number: regular expression
keywords:
  - keyword 1
  - keyword 2
options:
  currency: USD
  languages:
    - en
The defined attributes in the template described as:
•	issuer: Client name or the name of the invoice issuer, company name
•	keywords: Used to pick the correct template matching the invoice PDF.
Fields:
Required fields to be extracted are invoice amount, invoice date and invoice number using regular expression. We can even have more number of fields extracted.
Invoice Data to csv
Invoice data fields extracted from the invoice pdf files using regular expression, the results are written to csv file.
	
