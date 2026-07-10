# CSCI-2356 Natural Burial Project

This repository contains a web form project for CSCI-2356. The application presents natural burial options, lets users enter burial preferences, stores form data in browser local storage, and can exchange burial information with an Express server endpoint.

## Project Overview

The main project is in the `Natural Burial` directory. It includes:

- A Tailwind-based HTML form for selecting burial methods, grave locations, marker options, and an inscription.
- CSS styling for the page layout and form components.
- JavaScript for saving and displaying burial information.
- Audio clips connected to option cards and form submission feedback.
- Image assets for burial methods, locations, and marker options.
- A small Express server with GET and POST endpoints for burial information.

## Team Members

- Aakarshan Khosla
- Aarav Sen Mehta
- Bhabin Chudal
- Sadikshya Oli

## Folder Structure

```text
CSCI-2356/
├── INSTRUCTIONS.MD
├── README.md
└── Natural Burial/
    ├── templates/
    │   └── index.html
    └── static/
        ├── audio/
        ├── css/
        │   └── index.css
        ├── images/
        └── javascript/
            ├── audio.js
            ├── jquery-3.7.1.js
            ├── tailwind.config.js
            └── server/
                ├── client.js
                └── index.js
```

## Technologies Used

- HTML
- CSS
- JavaScript
- Tailwind CSS CDN
- jQuery
- Node.js
- Express

## Running the Project

### Open the Static Page

You can open the HTML file directly in a browser:

```text
Natural Burial/templates/index.html
```

### Run the Express Server

The server entry point is:

```text
Natural Burial/static/javascript/server/index.js
```

Install Express if it is not already installed:

```bash
npm install express
```

Start the server:

```bash
node "Natural Burial/static/javascript/server/index.js"
```

The server listens on port `3026`.

```text
http://localhost:3026
```

## Notes

- `client.js` currently points to `https://ugdev.cs.smu.ca:3026` for server requests.
- Form data is also stored in browser local storage under the `burial-info` key.
- Audio files are played when the user clicks the speaker icons and when the form is submitted.

## Course Phase

Phase 1 focuses on:

- `Natural Burial/templates/index.html`
- `Natural Burial/static/css/index.css`
- Image assets in `Natural Burial/static/images`
