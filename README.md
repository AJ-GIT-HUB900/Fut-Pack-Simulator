# Fut-Pack-Simulator
# EA FC Pack Simulator 

A lightweight, front-end web application that simulates opening EA Sports FC Ultimate Team packs. It uses realistic, weighted drop probabilities and dynamically loads thousands of players from a custom CSV database.

## Live Demo
[Insert your GitHub Pages link here, e.g., https://AJ-GIT-HUB900.github.io/fut-pack-simulator/]

## Features

* **Realistic Pack Weights:** Uses a weighted probability algorithm to simulate accurate drop rates (e.g., 75-79 rated players appear frequently, while 90+ rated players have a < 1% drop rate).
* **Dynamic Walkout Animations:** Automatically detects the highest-rated player in the pack and triggers a distinct "Walkout" CSS animation if they are rated 86 or higher.
* **CSV Database Integration:** Utilizes the PapaParse library to parse thousands of players directly from a `players.csv` file without needing a backend server.
* **Dynamic Valuation:** Automatically estimates the coin value of packed players based on their overall rating and calculates the profit/loss margin of each pack.
* **Club Economy:** Tracks user coin balances across pack openings.

## Technologies Used

* HTML5
* CSS3 (Flexbox, CSS Animations)
* Vanilla JavaScript (ES6)
* [PapaParse](https://www.papaparse.com/) (CSV parsing)

## How to Run Locally

If you want to run this project on your local machine:

1. Download or clone the repository to your computer.
2. Ensure both `index.html` and `players.csv` are in the same folder.
3. **Important:** Because the app fetches a local CSV file, opening `index.html` directly by double-clicking it may result in a CORS (Cross-Origin Resource Sharing) error in some browsers. To fix this, use a local server:
   * **VS Code:** Install the "Live Server" extension and click "Go Live".
   * **Python:** Open your terminal in the project folder and run `python -m http.server 8000`. Then open `http://localhost:8000` in your browser.

## Managing the Player Database

To update the players in the game, simply edit the `players.csv` file. The application requires the first row to be headers, specifically needing these exact column names:

`Name,Rating,Position`

**Example CSV Format:**
Name,Rating,Position
Kylian Mbappé,91,ST
Erling Haaland,91,ST
Jude Bellingham,86,CM
Harry Maguire,79,CB

*Note: The script automatically calculates a player's pack tier and coin value based on their `Rating` column, so you do not need to manually input market prices.*
