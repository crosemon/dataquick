dataquick
=========

Code for parsing and analytics of the Dataquick assessor and sales data

**Additional documentation**  
• [Indicators](https://github.com/ual/dataquick/blob/master/ucb_documentation/indicators.md)  
• [Data parsing procedures](https://github.com/ual/dataquick/blob/master/ucb_documentation/parsing_raw_data.md)

=========
#### Project background

We obtained a large dataset of parcel and sales transaction records from Dataquick, covering the entire state of California and going back 10 to 25+ years. The data was purchased by the California Air Resources Board (ARB) for research we are performing on their behalf about residential displacement that’s linked to transit-oriented development.

**Contacts**  
• Miriam Zuk, project manager – `mzuk@berkeley.edu`  
• Sam Maurer, performed the initial data parsing – `maurer@berkeley.edu`  
• Courtney Smith, ARB contact – `cesmith@arb.ca.gov`  
• Christopher LaPage, Dataquick account manager – `clapage@dataquick.com`  
• Juan Qui, Dataquick fulfillment contact – `jqui@dataquick.com`  

**Documentation from Dataquick**  
• "Layout" spreadsheets with database schema information  
• "Totals Report" spreadsheets with record counts by county  
• "Catalog/Data Dictionary" spreadsheet with more detailed field definitions  
• These are available from Box or FTP (see below)  

=========
#### Ways to access the data

1. Data is in Postgres on the UAL Tehran server  
• URL: `tehran.ual.berkeley.edu`  
• databse: `dataquick`, schema: `master` for the master version of the data tables  
• login: `dataquick_user`, password: `ucbdq`  
• tables: `assessor`, `sales`, `ahist`, `foreclosure`  
2. Raw data files and CSV county extracts are in a shared folder on Box (contact Miriam Zuk for access)
3. Raw data files are also available from Dataquick by FTP  
• URL: `ftp.dataquick.com`  
• login: `ucbrkly`, password: `2a3jsv13`

=========
#### Contents of raw data files

**Assessor**  
• one record per legal property  
• most recent snapshot, from 2013 or 2014 depending on the county  
• provided as one large fixed-width text file (dated 5-28-2014)  
• identical data provided as sequence of smaller tab-delimited files (dated 7-11-2014)  
• do not use intermediate tab-delimited version from June, which had formatting errors

**Assessor history**  
• yearly snapshots of records from each county (frequency varies beginning in 2012)  
• data covers 2004–2013 for all counties, plus 2014 for some counties  
• provided as sequence of large fixed-width text files (dated 7-20 or 7-21-2014)  
• do not use earlier May/June version of the files, which didn't match the schema

**Sales**  
• one record per transaction  
• covers 1988 to mid-2014, plus earlier transactions for certain counties  
• provided as one large fixed-width text file (dated 5-28-2014)  
• equivalent data provided as sequence of smaller tab-delimited files (dated 7-9-2014), including some additional transaction types  
• do not use intermediate tab-delimited version from June, which had formatting errors  
*check: do the later files also include additional records from the month of June?*

**Foreclosure**  
• provided as one large fixed-width text file (dated 5-28-2014)  
• same data also provided as a tab-delimited file (dated 6-16-2014)  
