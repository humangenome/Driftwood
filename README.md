<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="docs/img/driftwood-logo-dark.png">
    <img src="docs/img/driftwood-logo-light.png" alt="Driftwood" width="460">
  </picture>
</p>

<p align="center">
  <a href="#install"><img src="https://img.shields.io/badge/Platform-Windows_10%2F11%2FServer-blue.svg" alt="Platform"></a>
  <a href="https://store.steampowered.com/app/4001890/"><img src="https://img.shields.io/badge/Game-How_to_Fish-4aa3df.svg" alt="Game"></a>
  <a href="#how-many-players-can-join"><img src="https://img.shields.io/badge/Players-up_to_4-brightgreen.svg" alt="Players"></a>
  <a href="https://github.com/HumanGenome/DriftwoodServer"><img src="https://img.shields.io/badge/Server_Source-DriftwoodServer-444.svg" alt="Server Source"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-lightgrey.svg" alt="License"></a>
</p>

# Driftwood

**How to Fish** has no dedicated server. Its co-op runs in a Steam lobby on one player's PC, so the island is only there while that player is playing. Driftwood gives it one: [DriftwoodServer](https://github.com/HumanGenome/DriftwoodServer) runs the game headless on a Windows machine with its own address, and the Driftwood app takes your crew there.

Every player installs the Driftwood app to join. Your copy of How to Fish is still bought, launched and updated through Steam; Driftwood ships no part of it.

## Features

### 🧭 Join by IP, as yourself
Save a server's address once. The app shows whether it is up and who is on it, and **Connect** starts How to Fish and takes you in. The server loads your own saved character by your Steam account, whichever order your crew joins in. After your first Connect, you can also type the address into How to Fish's own **Join Game** box.

<p align="center">
  <img src="docs/img/app-v0.1.5-servers.png" alt="The Driftwood app with a How to Fish server online, two players on it with their time on the server, and the Connect button" width="860">
</p>

### 🖥️ Admin console
Server owners paste the admin password once and run the server from the Console tab: status, players, saves and snapshots, kick and block, a `[Server]` line in everyone's chat, the crew's shared wallet, moving the crew to another island, and sending a stuck player back to shore.

<p align="center">
  <img src="docs/img/app-v0.1.5-console.png" alt="The Driftwood app's Console tab connected to a server, after the world, version, money, blocked, players and snapshots commands" width="860">
</p>

### 💾 World backups
The server saves and checks the save is on disk before it takes a snapshot, so every backup is a whole world. From the app's World window, owners take a snapshot, download one, restore an earlier world, upload a save from their own PC, or bring the latest snapshot over from another of their servers.

<p align="center">
  <img src="docs/img/app-v0.1.5-world-backups.png" alt="The Driftwood app's World window: the server's snapshots with date, time, kind and size, and the Take snapshot, Refresh, Download and Restore buttons" width="620">
</p>

### Also on the server
- **Chat commands:** players type `!help`, `!stuck` (back to the island spawn), `!playtime` and `!top` into How to Fish's own chat.
- **A catch leaderboard:** every sale at the sell box is credited to the player who caught the fish, and the board keeps catches, earnings, bosses and playtime. `!top` shows it in game; the console's `top` shows the full table.
- **Discord alerts:** point the server at a Discord webhook and it posts joins and leaves, boss kills, island moves and blocked join attempts.

## Install

### Rent a server
[How to Fish hosting from SurvivalServers.com](https://www.survivalservers.com/services/game_servers/how_to_fish/?utm_source=github&utm_medium=readme_install&utm_campaign=driftwood) comes with Driftwood installed, the ports open, and an address ready to hand to your players.

### Players
1. Download `DriftwoodSetup-<version>.exe` from the [latest release](https://github.com/HumanGenome/Driftwood/releases/latest).
2. Run the installer. It is a one-time install per person.
3. Open Driftwood, add the server address your host gave you, and click **Connect**. The app readies How to Fish and takes you in.

### Self-hosted servers
The walkthrough is [DriftwoodServer's README](https://github.com/HumanGenome/DriftwoodServer#readme). You need a Windows machine, a copy of How to Fish's game files on it (from your own Steam copy; the server package ships no part of the game), and two open ports: the game port and the status port directly above it.

A server is the game itself with no renderer and a small mod inside it, and the server package is under a megabyte on top of the game's files. Before it changes anything in the game, the server checks every piece it depends on. If a game update moved one, it refuses to host and names what moved, and it reports ready only once the world is running.

### Admin password
The app's Console tab and World window ask for the server's admin password. It is not the password players join with, and players never need it. The app keeps it on your PC only.

- **Rented server:** your host shows it with your server's details.
- **Self-hosted:** it is the `authToken` you set in the server's config ([step 5 of DriftwoodServer's README](https://github.com/HumanGenome/DriftwoodServer#5-fill-in-the-config-and-pin-the-build)).

## Releases

This repo publishes the player side:

- `DriftwoodSetup-<version>.exe`, the installer for players
- Release notes for each version

The server package for hosts lives on the [DriftwoodServer release page](https://github.com/HumanGenome/DriftwoodServer/releases/latest). What changed in the app is in [this repo's release notes](https://github.com/HumanGenome/Driftwood/releases); what changed on the server side is in [DriftwoodServer's CHANGELOG.md](https://github.com/HumanGenome/DriftwoodServer/blob/master/CHANGELOG.md).

## Source

The server's source is public at [HumanGenome/DriftwoodServer](https://github.com/HumanGenome/DriftwoodServer). The app ships as release binaries from this repo.

Players only need this repo's releases; hosts run the server from DriftwoodServer's.

## FAQ

### Does everyone need the app?
Yes. How to Fish on its own cannot connect to a Driftwood server, so every player installs the app first.

### How many players can join?
Up to four, the number Dazed Games gives on How to Fish's [Steam page](https://store.steampowered.com/app/4001890/). The game's own lobby code makes room for more, but we have not seen more than four people play together. The host sets the server's slot count, and the server checks it before letting anyone in, so a full server turns the next player away cleanly instead of half-admitting them.

### Does it change my game?
On your first Connect, the app copies a small mod loader (BepInEx) and the Driftwood join mod into your How to Fish folder. The mod only steps in on joins to a Driftwood server; single-player and Steam lobbies play as before.

### Where is my character saved?
On the server, with the world, under your Steam account.

### Does the app update itself?
Yes. It checks for a new version when it starts and finishes the update after you close the game. Every update is signed, and the app refuses one that is not. Settings can turn the check off.

### Is Linux supported?
No. The app and the server are Windows only.

### Is this official?
No. Driftwood is an independent project. Dazed Games does not ship dedicated servers for How to Fish.

### Something broke
[Open an issue](https://github.com/HumanGenome/Driftwood/issues). If you rent a server, your host handles billing and control panel questions.

## Contributing

Bug reports and feature requests are welcome; see [CONTRIBUTING.md](CONTRIBUTING.md). Security issues go through [private reporting](.github/SECURITY.md), never a public issue.

## Community note

Driftwood is a community project and is not affiliated with, endorsed by, or supported by Dazed Games. How to Fish is their game: [buy it on Steam](https://store.steampowered.com/app/4001890/).

## License

MIT. See [LICENSE](LICENSE).

## Credits

- [BepInEx](https://github.com/BepInEx/BepInEx), the Unity modding framework the server side runs on
- [Avalonia](https://avaloniaui.net/), the .NET UI framework used by the Driftwood app
