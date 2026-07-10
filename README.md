# CSCI-2356 Natural Burial Project

An interactive web form for exploring natural burial options, collecting user preferences, playing related audio descriptions, and saving burial information through browser storage and an Express endpoint.

![HTML](https://img.shields.io/badge/HTML-5-E34F26)
![CSS](https://img.shields.io/badge/CSS-3-1572B6)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6-F7DF1E)
![Tailwind](https://img.shields.io/badge/Tailwind-CDN-38B2AC)
![Node](https://img.shields.io/badge/Node.js-Express-339933)

## At a Glance

| Area | Details |
| --- | --- |
| Project | Natural burial preference form |
| Course | CSCI-2356 |
| Frontend | HTML, CSS, JavaScript, Tailwind CSS CDN, jQuery |
| Backend | Node.js and Express |
| Data | Browser local storage and server GET/POST endpoints |
| Media | Image cards and audio playback for burial choices |

## Experience Flow

```mermaid
flowchart LR
    Start([User opens form]) --> General[Enter personal details]
    General --> Method[Choose burial method]
    Method --> Location[Choose grave location]
    Location --> Marker[Choose marker option]
    Marker --> Quote[Add inscription or quote]
    Quote --> Save[Save form data]
    Save --> Local[(Browser local storage)]
    Save --> Server[(Express endpoint)]
    Local --> Display[Reload saved choices]
    Server --> Display
```

## Application Architecture

```mermaid
flowchart TB
    Browser[Browser UI] --> HTML[index.html]
    HTML --> Styles[index.css]
    HTML --> Audio[audio.js]
    HTML --> Client[client.js]
    HTML --> Images[Image assets]
    HTML --> Clips[Audio assets]

    Client --> LocalStorage[(localStorage: burial-info)]
    Client --> API[Express API]

    API --> GetEndpoint[GET /burialInfoEndpoint]
    API --> PostEndpoint[POST /burialInfoEndpoint]
    API --> ServerState[(burial_data object)]
```

## Data Lifecycle

```mermaid
sequenceDiagram
    participant User
    participant Form as Web Form
    participant Storage as Local Storage
    participant API as Express Server

    User->>Form: Selects burial options
    User->>Form: Submits form
    Form->>Storage: Saves burial-info JSON
    Form->>API: Sends POST request
    API-->>Form: Returns saved burial data
    User->>Form: Loads saved information
    Form->>API: Sends GET request
    API-->>Form: Returns burial data
    Form->>Storage: Updates local copy
```

## Feature Map

```mermaid
mindmap
  root((Natural Burial Form))
    Personal Details
      Name
      Phone
      Email
      Date of birth
      Number of places
    Burial Methods
      Casket
      Ecoffin
      Shroud
      Tree pod
    Grave Locations
      Camp Hill
      Fairview Lawn
      St. Peters
      Mount Hermon
    Marker Options
      Wooden cross
      Stone marker
      Wooden plaque
      Tree marker
    Feedback
      Audio descriptions
      Submit sound
      Saved form values
```

## Team Members

- Aakarshan Khosla
- Aarav Sen Mehta
- Bhabin Chudal
- Sadikshya Oli

## Folder Structure

```text
CSCI-2356/
|-- INSTRUCTIONS.MD
|-- README.md
`-- Natural Burial/
    |-- templates/
    |   `-- index.html
    `-- static/
        |-- audio/
        |-- css/
        |   `-- index.css
        |-- images/
        `-- javascript/
            |-- audio.js
            |-- jquery-3.7.1.js
            |-- tailwind.config.js
            `-- server/
                |-- client.js
                `-- index.js
```

## Running the Project

### Option 1: Open the Static Page

Open this file directly in a browser:

```text
Natural Burial/templates/index.html
```

This is useful for reviewing the layout, images, audio buttons, and local-storage behavior.

### Option 2: Run the Express Server

The server entry point is:

```text
Natural Burial/static/javascript/server/index.js
```

Install Express if it is not already available:

```bash
npm install express
```

Start the server:

```bash
node "Natural Burial/static/javascript/server/index.js"
```

Then open:

```text
http://localhost:3026
```

## Important Notes

- The Express server listens on port `3026`.
- `client.js` currently points to `https://ugdev.cs.smu.ca:3026` for server requests.
- Form data is stored in local storage using the `burial-info` key.
- Audio clips play when users select speaker icons and when the form is submitted.

## Course Phase

Phase 1 focuses on:

- `Natural Burial/templates/index.html`
- `Natural Burial/static/css/index.css`
- Image assets in `Natural Burial/static/images`
