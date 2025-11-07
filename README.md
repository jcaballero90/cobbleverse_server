# Cobbleverse Server In Docker Compose
## 

## Credits
Credits to Blue-Kachina for the original solution (https://github.com/Blue-Kachina/cobbleverse_server)

## Changes
1) Removed sponge dependency.
2) Updated Forge and Cobbleverse versions to 07/11/2025.
3) Fixed an issue where the `flatten_dp` function in `install-modpack.sh` was removing the `datapacks` folder.  
   The absence of datapacks caused a bug where a red chat message appeared saying "Unknown series: kanto", and prevented the player from receiving the Pokédex and Trainer Card after selecting their first Pokémon.

## What Exactly Is This?
### Cobbleverse
Cobbleverse is a modpack (collection of mods) for Java Minecraft that bring an experience much like the main series of Pokemon games to the world of Minecraft

### Docker
Docker is a way of containerizing applications and their dependencies, and does so in a way very akin to virtual machines

### This Particular Solution
This solution will help you set up your own Cobblemon server

## Instructions
### First Run
1) Ensure that you already have Docker/Docker Compose installed
2) Clone the repository
3) Go to https://modrinth.com/modpack/cobbleverse/versions, right click your desired download version button and select "Copy link address"
4) Replace MODRINTH_URL with the link obtained in the third step
5) If you want to use the env.file, set up your desired variable values and change its name from .env.example to .env. If you don't, replace the values directly after the hyphen in the docker-compose.yml file 
   ("${MODRINTH_URL:-URL}"), same for all other variables.
6) Navigate to the folder you cloned this repo to
7) Run the command: `docker-compose up -d` This will instantiate your server (will probably take a minute or two)

#### What will happen when I do this?
1) The system will check to see if the worldname you specified has already been used
2) Assuming it has not, then it will create a new folder for the world
3) If this is a new world, then the mods that make up this modpack will all be downloaded, and saved to the server in the proper spot
4) Next the Minecraft server is started up

### Recommendations
Download from Modrinth the client with the same version used for the server setup. Remember that client and server MUST have the same version.
