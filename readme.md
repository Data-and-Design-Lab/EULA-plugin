# Sms Spoof Detector

[![Python Version][npm-image]][npm-url]
[![FastAPI Version][node-image]][node-url]
[![Scikit Version][openai-image]][openai-url]

The EULA Privacy Nudge Tool is an innovative research-driven project designed to address the critical issue of user comprehension in software End User License Agreements (EULAs). Our tool aims to improve user awareness and understanding of privacy-related clauses through intelligent visual emphasis and natural language processing techniques.

## Features

- **Intelligent Keyword Identification:** Uses natural language processing to detect privacy-sensitive terms
- **Visual Emphasis:** Highlights critical privacy-related clauses
- **Comprehensive Analysis:** Focuses on data collection, sharing, and security provisions

## Installation

### Step 1: Clone the Repository

Clone this repository to your local machine and cd to the directory:

```bash
git clone https://github.com/Data-and-Design-Lab/EULA-plugin
cd EULA-plugin
```

### Step 2: Install Dependencies

This project utilizes npm for dependency management. Run the following command to install all dependencies:

```bash
npm install
```

If you do not have `npm` installed, you can download it from https://nodejs.org/en/download/.

### Step 3: Update Webpack Configuration

Create a webpack.config.js file in your project directory. This file will configure how Webpack bundles your code:

```js
const path = require("path");

module.exports = {
  entry: "./contentScript.js", // Adjust the entry point as needed
  mode: "development", // or 'production'
  output: {
    filename: "contentBundle.js", // Name of the bundled file
    path: path.resolve(__dirname, "dist"), // Output directory
  },
};
```

> [!WARNING]
> Make sure to replace `contentScript.js` with the correct path to your content script file.

### Step 4: Bundle Your Content Script

In your terminal, run Webpack to bundle your content script:

```bash
npx webpack --config webpack.config.js
```
This will create a contentBundle.js file in the dist directory.

### Step 5: Update Manifest

Open your `manifest.json` file and update the `content_scripts` section to use the bundled script:

```json
"content_scripts": [
  {
    "matches": ["<all_urls>"],
    "js": ["dist/contentBundle.js"] // Update the path accordingly
  }
]
```
Now you can load the extension into Chrome and test it to ensure that the bundled content script works as expected.

## Contributing

1. Fork the [repository][project-url]
2. Create your own feature branch (`git checkout -b feature/fooBar`)
3. Commit your changes (`git commit -am 'Add some fooBar'`)
4. Push to your branch (`git push origin feature/fooBar`)
5. Create a new PR (Pull Request)

<!-- Markdown link & img dfn's -->
[npm-image]: https://img.shields.io/badge/v9.0.0-CB3837?style=flat-square&logo=npm&logoColor=ffffff&label=npm
[npm-url]: https://www.npmjs.com/
[node-image]: https://img.shields.io/badge/v22.12.0-5FA04E?style=flat-square&logo=nodedotjs&logoColor=ffffff&label=nodejs
[node-url]: https://nodejs.org/en
[openai-image]: https://img.shields.io/badge/v4.76.3-412991?style=flat-square&logo=openai&logoColor=ffffff&label=openai
[openai-url]: https://openai.com/
[project-url]: https://github.com/Data-and-Design-Lab/EULA-plugin