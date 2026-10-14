<p align="center">
  <img src="docs/img/driftwood-lockup.png" alt="Driftwood" width="440">
</p>

# Driftwood

[![Platform](https://img.shields.io/badge/Platform-Windows_10%2F11%2FServer-blue.svg)](#install)
[![Game](https://img.shields.io/badge/Game-How_to_Fish-4aa3df.svg)](https://store.steampowered.com/app/4001890/)
[![Players](https://img.shields.io/badge/Players-up_to_8-brightgreen.svg)](#-up-to-eight-players)
[![Server Source](https://img.shields.io/badge/Server_Source-DriftwoodServer-444.svg)](https://github.com/HumanGenome/DriftwoodServer)
[![License](https://img.shields.io/badge/License-MIT-lightgrey.svg)](LICENSE)

**How to Fish** has no dedicated server. Its co-op runs in a Steam lobby hosted from one player's game, so the world is only there while that player is playing. Driftwood adds a How to Fish dedicated server: [DriftwoodServer](https://github.com/HumanGenome/DriftwoodServer) runs the game headless on a Windows machine with a public IP and port, and the Driftwood app connects players to it by address.

Every player must install Driftwood to join a Driftwood server. Stock How to Fish cannot connect to a Driftwood server directly. Your copy of the game is still bought, launched and updated through Steam; Driftwood ships no part of it.

<p align="center">
  <img src="docs/img/launcher.png" alt="The Driftwood app with a How to Fish server online and three players on it" width="860">
</p>

## Features

### 🧭 Join by address
Save a server's address once. The app then shows whether it is up and who is on it, and **Connect** starts How to Fish and takes you straight in.

### 💬 Chat commands in the game's own chat
Players type `!help`, `!stuck` (back to the island spawn), `!playtime` and `!top` into How to Fish's chat.

### 🏆 A catch leaderboard
The server credits every sale at the sell box to the player who caught the fish and keeps a board of catches, earnings, bosses and playtime. `!top` shows it in game; the console's `top` shows the full table.

### 🖥️ An admin console built in
Server owners sign in with their admin password and drive the server from the Console tab: status, players, saves and snapshots, kick and block, a `[Server]` line in everyone's chat, the shared wallet, moving the crew to another island, and sending a stuck player back to shore.

<p align="center">
  <img src="docs/img/console.png" alt="The Console tab connected to a server, showing status and the player list" width="860">
</p>

### 💾 Backups that are actually consistent
The server saves and confirms the save is on disk before a snapshot is taken, so a backup is a whole world. Owners list and restore them from the app.

<p align="center">
  <img src="docs/img/world-backups.png" alt="The World backups dialog listing snapshots with full timestamps and sizes" width="620">
</p>

### 🔔 Discord alerts
Point the server at a Discord webhook and it posts joins and leaves, boss kills, island moves and blocked join attempts.

### 🧑‍🤝‍🧑 Up to eight players
The server enforces its slot count before a player gets in, so a full server turns the next player away cleanly instead of half-admitting them.

### 🚦 Says why when it cannot host
Before it changes anything in the game, the server checks every piece it depends on. If a game update moved one, it refuses to host and names what moved in one sentence, instead of opening a port with nothing behind it. It reports ready only once the world is running.

### 🪶 Light on the machine
One server is the game itself with no renderer and a small mod inside it, so one machine can host several. The server package is under a megabyte on top of How to Fish's own files.

## Install

### Rent a server
[How to Fish hosting from SurvivalServers.com](https://www.survivalservers.com/services/game_servers/how_to_fish/?utm_source=github&utm_medium=readme_install&utm_campaign=driftwood) comes with Driftwood installed, the ports open, and an address ready to hand to your players.

### Players
1. Download `DriftwoodSetup-<version>.exe` from the [latest release](https://github.com/HumanGenome/Driftwood/releases/latest).
2. Run the installer. It is a one-time install per person.
3. Open Driftwood, add the server address your host gave you, and click **Connect**. The app readies How to Fish and takes you in.

### Self-hosted servers
The walkthrough is [DriftwoodServer's README](https://github.com/HumanGenome/DriftwoodServer#readme). You will need a Windows machine, a copy of How to Fish's game files on it (from your own Steam copy; the server package ships no part of the game), and two open ports: the game port and the status port directly above it.

### Admin password
The app's Console tab and World backups ask for the server's admin password. It is not the password players join with, and players never need it. The app keeps it on your PC only.

- **Rented from SurvivalServers.com:** it is printed on your server's page in the control panel, under Driftwood Admin.
- **Self-hosted:** it is the `authToken` you set in the server's config ([step 5 of DriftwoodServer's README](https://github.com/HumanGenome/DriftwoodServer#5-fill-in-the-config-and-pin-the-build)).

## Releases

This repo publishes the player side:

- `DriftwoodSetup-<version>.exe`, the installer for players
- Release notes for each version

The server package for hosts lives on the [DriftwoodServer release page](https://github.com/HumanGenome/DriftwoodServer/releases/latest). What changed in the app is in [this repo's release notes](https://github.com/HumanGenome/Driftwood/releases); what changed on the server side is in [DriftwoodServer's CHANGELOG.md](https://github.com/HumanGenome/DriftwoodServer/blob/master/CHANGELOG.md).

## Source

The server's source is public at [HumanGenome/DriftwoodServer](https://github.com/HumanGenome/DriftwoodServer). The app ships as release binaries from this repo.

Players only need this repo's releases; hosts run the server from DriftwoodServer's.

## Contributing

Bug reports and feature requests are welcome; see [CONTRIBUTING.md](CONTRIBUTING.md). Security issues go through [private reporting](.github/SECURITY.md), never a public issue.

## Community Note

Driftwood is a community project and is not affiliated with, endorsed by, or supported by Dazed Games. How to Fish is their game: [buy it on Steam](https://store.steampowered.com/app/4001890/).

## License

MIT. See [LICENSE](LICENSE).

## Credits

- [BepInEx](https://github.com/BepInEx/BepInEx), the Unity modding framework the server side runs on
- [Avalonia](https://avaloniaui.net/), the .NET UI framework used by the Driftwood app
