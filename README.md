# Telegram Movie Bot

A Telegram bot that searches for movies and shows their details. It is built with [pyTelegramBotAPI](https://github.com/eternnoir/pyTelegramBotAPI) and gets its data from the [OMDb API](https://www.omdbapi.com/).

## Features

- **Search:** type a movie name and get up to 5 matching results as buttons
- **Popular:** a list of popular movies (Inception, Interstellar, The Dark Knight, Avengers, Titanic)
- **Movie details:** tap a movie to see its year, IMDb rating, runtime, genre, director, actors and full plot
- Reply keyboard with `Search`, `Popular` and `Help` buttons

## Bot commands

| Command | Description |
|---------|-------------|
| `/start` | Show the welcome message and the buttons |
| `/search` | Ask for a movie name and search for it |
| `/popular` | Show the popular movies |
| `/help` | Show the help message |

## Files

| File | Description |
|------|-------------|
| `app.py` | The bot: commands, buttons and message handlers. |
| `app_api.py` | Functions that call the OMDb API (search, movie info, popular movies). |
| `base.py` | Your private settings (bot token and API key). **Not included in the repository. You create it.** |

## Requirements

- Python 3
- A Telegram bot token from `@BotFather`
- A free OMDb API key from [omdbapi.com/apikey.aspx](https://www.omdbapi.com/apikey.aspx)
- The packages in `requirements.txt`: `pyTelegramBotAPI` and `requests`

## Installation

```bash
pip install -r requirements.txt
```

## Configuration

Create a file named `base.py` next to `app.py` and put your own values in it:

```python
TOKEN = "your-telegram-bot-token"
API_KEY = "your-omdb-api-key"
```

`base.py` is listed in `.gitignore`, so your token and key are never uploaded to GitHub.

## Usage

```bash
python app.py
```

When the terminal prints `bot created...`, open your bot in Telegram and send `/start`. The bot works only while the script is running.

## Notes

- Search shows the first 5 results.
- The popular list is fixed in `app_api.py`. Edit the `popular_movies` list to change it.
- Keep your token and API key private. If one of them is ever shared by mistake, create a new one (a new bot token from `@BotFather`, a new key from OMDb).
