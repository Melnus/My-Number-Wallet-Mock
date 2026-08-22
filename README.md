# Selective Disclosure Digital ID Wallet Mockup

This project is a Proof of Concept (PoC) and user interface mockup for a digital identity wallet. It is designed to demonstrate the mechanism of "Selective Disclosure."

Through this application, users can experience how specific information (claims) can be extracted from multiple digital credentials (Verifiable Credentials) and generated into a Verifiable Presentation (VP) tailored to a verifier's specific requirements, rather than presenting the entirety of the original credentials.

## Live Demonstration

A live demonstration of this application is hosted on GitHub Pages and can be accessed at:  
[https://melnus.github.io/My-Number-Wallet-Mock/](https://melnus.github.io/My-Number-Wallet-Mock/)


## Key Features

*   **Credential Management**: Displays fictional dummy data for various credentials, including identity, tax records, health insurance, and pension information, formatted as digital cards.
*   **Selective Disclosure Simulation**: Simulates the following presentation scenarios to demonstrate privacy preservation:
    *   Age Verification: Presents only the proof of being over a certain age (`isOver20`), strictly concealing the date of birth and full name.
    *   Loan Application: Presents only the individual's name and proof of income exceeding a specific threshold (`isIncomeOver300k`), concealing exact income figures.
    *   Administrative Procedures: Presents only the individual's name, address, and taxation status.
*   **Verifiable Presentation (VP) Preview**: Allows users to preview the exact JSON data format that would be transmitted to a verifier during a disclosure event.
*   **Audit Logging**: Records a history of when, to whom, and what information was presented. This data is stored entirely client-side utilizing the browser's Local Storage.

## Technical Specifications

*   HTML5 / CSS3 / Vanilla JavaScript.
*   The data structure is modeled after the W3C Verifiable Credentials (VC) data model for demonstration purposes.
*   This is a standalone front-end application. It does not communicate with external databases, APIs, or server-side environments.

## Local Execution Guide

To run this application locally, a local web server is required. The application utilizes the Fetch API to load local JSON files, which will be blocked by CORS policies if the `index.html` file is opened directly via the `file://` protocol.

1.  Clone or download this repository to your local machine.
2.  Start a local HTTP server in the root directory of the project.
    *   Using Python 3: `python -m http.server 8000`
    *   Using Node.js: `npx serve` or `npx http-server`
3.  Access `http://localhost:8000` (or the corresponding port assigned by your server) via a web browser.

## Directory Structure

```text
My-Number-Wallet-Mock/
├── index.html        # Main application (HTML/CSS/JS)
├── json/             # Mock data (Verifiable Credentials)
│   ├── identity.json # Identity credential
│   ├── tax.json      # Tax and income credential
│   ├── health.json   # Health insurance credential
│   └── pension.json  # Pension credential
├── LICENSE           # License file
└── README.md         # This document
```

## Disclaimer

*   **This application is strictly a prototype intended solely for conceptual demonstration.**
*   All credentials and personal information displayed within the application are entirely fictional dummy data.
*   This application does not perform actual cryptographic signing, authentication, or communication with any real-world government agencies, financial institutions, or insurers.
*   It cannot be used for actual identity verification, official administrative procedures, or real-world transactions.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
