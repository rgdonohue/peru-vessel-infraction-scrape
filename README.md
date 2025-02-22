# Peru Fishing Vessel Seizures, Confiscations, and Investigations

This project analyzes data from Peru's Ministry of Production (PRODUCE) regarding fishing vessels that have previously been seized, confiscated, or investigated for illegal activities, but are now considered verified and operational under Legislative Decree N° 1392.

## Data Source

The data is scraped from the SIFORPA (Sistema de Formalización Pesquera Artesanal) portal:
https://transparencia.produce.gob.pe/index.php/pesca-artesanal/siforpa/listado-de-embarcaciones-para-el-decreto-legislativo-n-1392

## Methodology

The data collection process involves:

1. Web scraping using Python with:
   - Selenium WebDriver for browser automation
   - BeautifulSoup4 for HTML parsing
   - Chrome WebDriver for rendering JavaScript content

2. The scraper navigates through paginated results (approximately 249 pages with 10 vessels per page)

3. For each vessel, we collect:
   - Unique ID number
   - Registration date
   - Document number
   - Fisher's name
   - Vessel registration number
   - Vessel name
   - Legal registration number
   - Protocol number

## Output

The scraped data is saved to `data/vessel_data.csv` with the following columns:
- unique_id: Vessel's unique identifier
- inscripcion: Registration date
- documento: Document number
- pescador: Fisher's name
- matricula: Vessel registration number
- embarcacion: Vessel name
- matricula_leg: Legal registration number
- protocolo: Protocol number

The dataset contains approximately 2,500 vessels with complete records.

## Requirements

- Python 3.x
- Chrome WebDriver
- Python packages:
  - selenium
  - beautifulsoup4
  - csv

## Usage

Run the Jupyter notebook `notebooks/scrape-vessels-data.ipynb` to collect the data. The notebook includes detailed logging of the scraping process and saves the results automatically to the CSV file.
