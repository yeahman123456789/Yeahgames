# Yeahgames
yeahman
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>GameHub – 500+ Free Games</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>GameHub</h1>
        <input id="search" type="text" placeholder="Search games...">
    </header>

    <div id="game-list"></div>

    <iframe id="game-frame" style="display:none;"></iframe>

    <script src="games.js"></script>
    <script src="script.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    background: #111;
    color: #fff;
    margin: 0;
    padding: 0;
}

header {
    background: #222;
    padding: 20px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

#search {
    width: 250px;
    padding: 10px;
    border-radius: 6px;
    border: none;
}

#game-list {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
    gap: 20px;
    padding: 20px;
}

.game-card {
    background: #1e1e1e;
    padding: 15px;
    border-radius: 10px;
    cursor: pointer;
    transition: 0.2s;
}

.game-card:hover {
    background: #333;
}

#game-frame {
    width: 100%;
    height: 90vh;
    border: none;
}
const games = [
    {
        name: "Snake",
        file: "games/snake/index.html"
    },
    {
        name: "Pong",
        file: "games/pong/index.html"
    },
    {
        name: "Flappy Block",
        file: "games/flappy/index.html"
    }
    // Add more games here
];
const gameList = document.getElementById("game-list");
const gameFrame = document.getElementById("game-frame");
const searchInput = document.getElementById("search");

function loadGames(filter = "") {
    gameList.innerHTML = "";

    games
        .filter(g => g.name.toLowerCase().includes(filter.toLowerCase()))
        .forEach(game => {
            const card = document.createElement("div");
            card.className = "game-card";
            card.textContent = game.name;

            card.onclick = () => {
                gameFrame.src = game.file;
                gameFrame.style.display = "block";
                window.scrollTo(0, 0);
            };

            gameList.appendChild(card);
        });
}

searchInput.addEventListener("input", () => {
    loadGames(searchInput.value);
});

loadGames();
#!/bin/bash

# List of open-source game URLs (GitHub repositories or direct links)
game_urls=(
    "https://github.com/johnfarrell/canvas-snake"
    "https://github.com/justmarkham/flappy-bird"
    "https://github.com/gabrielecirulli/2048"
    "https://github.com/josephg/tetris"
    "https://github.com/nosir/ponz"
)

# Download each game to a specific folder
for url in "${game_urls[@]}"; do
    folder_name=$(basename "$url")
    git clone "$url" "/path/to/your/website/games/$folder_name"
done

echo "All games have been downloaded and organized!"
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>YeahManGames – 500+ Free Games</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>YeahManGames</h1>
        <input id="search" type="text" placeholder="Search games...">
    </header>

    <div id="game-list"></div>

    <iframe id="game-frame" style="display:none;"></iframe>

    <script src="games.js"></script>
    <script src="script.js"></script>
</body>
</html>
