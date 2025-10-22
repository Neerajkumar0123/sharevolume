# Company Shares Outstanding Dashboard

This single-file HTML application provides a dynamic view of a company's Common Stock Shares Outstanding data fetched directly from the SEC EDGAR API. It highlights the maximum and minimum shares outstanding for fiscal years after 2020.

## Features

- **Dynamic Data Fetching**: Retrieves company data using CIK (Central Index Key) from the SEC EDGAR API.
- **Responsive Design**: Built with Tailwind CSS for a modern, mobile-friendly interface.
- **Max/Min Shares Display**: Clearly shows the highest and lowest reported shares outstanding, along with their respective fiscal years, for data after 2020.
- **Interactive CIK Input**: Supports changing the displayed company data by appending a CIK to the URL.
- **Attachment Reference**: Includes a reference to `uid.txt` as specified.

## Setup

No special setup is required. Simply save the `index.html` file and `uid.txt` in the same directory and open `index.html` in your web browser.

## Usage

### Default Company (AutoZone)

Upon opening `index.html`, the application will default to displaying data for AutoZone (CIK: `0000866787`).

### Viewing Other Companies

To view data for a different company, append its 10-digit CIK to the URL as a query parameter. For example:

- To view data for Apple Inc. (CIK: `0000320193`):
  `index.html?CIK=0000320193`

- To view data for Microsoft Corporation (CIK: `0000789019`):
  `index.html?CIK=0000789019`

The application will fetch and display the new company's data without requiring a page reload.

## Data Source

All financial data is fetched from the U.S. Securities and Exchange Commission (SEC) EDGAR API.

## Important Note on SEC API Access

Direct browser-based `fetch()` calls to the SEC EDGAR API may be subject to Cross-Origin Resource Sharing (CORS) policies. To mitigate this in a single-file application context, a public CORS proxy (`https://api.allorigins.win/raw?url=`) is utilized. For production environments or higher volume requests, it's recommended to implement a dedicated backend proxy to handle API requests, manage rate limits, and ensure compliance with SEC usage policies, including setting a descriptive `User-Agent` header. The `User-Agent` header in this client-side application is set as `AutoZoneApp/1.0 (noreply@example.com)`.

## Attachments

- `uid.txt`: An example attachment referenced within the `index.html` file.