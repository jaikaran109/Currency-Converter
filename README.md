# Currency Converter

A lightweight, real-time currency converter built with vanilla JavaScript, HTML, and CSS. It converts between major world currencies using live exchange rates and updates instantly as you type or change a currency.

## Demo

🔗 **Live Demo:** [jaikaran109.github.io/Currency-Conerter](https://jaikaran109.github.io/Currency-Conerter/)

Pick a source and target currency, enter an amount, and the converted value plus the live exchange rate appear automatically — no page reload required.

## Features

- **Live exchange rates** pulled from a public currency API
- **Bidirectional conversion** between any of the supported currencies
- **Instant updates** on input or currency change (no submit button needed)
- **Exchange rate display** showing the current rate between the two selected currencies
- **Zero dependencies** — pure HTML, CSS, and JavaScript

## Supported Currencies

| Code | Currency |
|------|----------|
| USD  | US Dollar |
| EUR  | Euro |
| GBP  | British Pound |
| INR  | Indian Rupee |
| CAD  | Canadian Dollar |
| AUD  | Australian Dollar |
| JPY  | Japanese Yen |

## Tech Stack

- **HTML5** — structure and markup
- **CSS3 (Flexbox)** — layout and styling
- **JavaScript (ES6)** — DOM manipulation and API integration
- **[ExchangeRate-API](https://www.exchangerate-api.com/)** — live exchange rate data
- **Fetch API** — handles HTTP requests to the exchange rate service

## Project Structure

```
currency-converter/
├── index.html      # Markup for the converter UI
├── app.js           # Conversion logic and API calls
├── style.css        # Styling and layout
└── README.md        # Project documentation
```

## Getting Started

### Prerequisites

- A modern web browser
- An internet connection (required for live exchange rate data)
- A free API key from [exchangerate-api.com](https://www.exchangerate-api.com/) (see [Configuration](#configuration))

### Installation

```bash
git clone https://github.com/<your-username>/currency-converter.git
cd currency-converter
```

No build step or package installation is required. The project runs entirely in the browser.

### Running Locally

Simply open `index.html` in your browser, or serve it with a lightweight local server:

```bash
npx serve .
```

## Configuration

This project calls the ExchangeRate-API to fetch live rates:

```
https://v6.exchangerate-api.com/v6/{API_KEY}/latest/{CURRENCY_CODE}
```

To use your own API key:

1. Sign up for a free key at [exchangerate-api.com](https://www.exchangerate-api.com/).
2. In `app.js`, replace the placeholder in the fetch URL with your key.

> **Security note:** Avoid committing real API keys to a public repository. For a production deployment, route the request through a small backend or serverless function so the key isn't exposed in client-side code.

## Usage

1. Select a source currency from the first dropdown.
2. Select a target currency from the second dropdown.
3. Enter an amount in the first input field.
4. The converted amount and current exchange rate update automatically.

**Example:** Converting 100 USD to INR — select `USD` → `INR`, enter `100`, and the result appears instantly in the second field.

## How It Works

1. DOM elements (selects, inputs, and the rate display) are referenced on load.
2. `updateRate()` runs once on page load to populate live data immediately.
3. Event listeners on the currency dropdowns and amount input trigger `updateRate()` on any change.
4. The function fetches the latest rates for the selected source currency, extracts the rate for the target currency, updates the displayed rate, and recalculates the converted amount.

## Known Limitations / Roadmap

- No error handling yet for failed API requests or network issues
- No loading indicator while a request is in flight
- Layout centering could be refined for smaller screens
- Consider migrating from `getElementById` to `querySelector` for consistency
- A backend proxy would improve API key security for production use

## Contributing

Contributions are welcome. To contribute:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes
4. Open a pull request

## License

This project is open source and available under the [MIT License](LICENSE).

## Author

Built as a learning project for practicing DOM manipulation, event handling, and API integration in vanilla JavaScript.
