# Cops vs Robbers

A real-time multiplayer implementation of the classic game of tag, featuring a cops-and-robbers theme with AWS-powered networking.

## Game Overview

Players engage in an intense chase where one player controls a police officer attempting to capture a thief (controlled by another player) who's trying to escape. The game features:

- Multiple challenging levels with increasing difficulty
- Unique perspective mechanics where police and thief players see different views
- Strategic hidden traps that affect player movement
- Real-time multiplayer functionality powered by AWS

## Technical Implementation

The multiplayer functionality is implemented using:
- Java ServerSocket for handling network connections
- Multi-threaded architecture for handling real-time communication
- TCP/IP protocol for reliable data transmission
- Server running on port 45371

## Features

- **Dynamic Perspectives**: Each level introduces different viewpoints for both roles, adding strategic depth
- **Trap System**: Interactive environment hazards that players must navigate
- **Real-time Multiplayer**: Low-latency gameplay experience through AWS infrastructure
- **Progressive Difficulty**: Each level introduces new challenges and mechanics

### Server Architecture
- Supports exactly 2 players
- Maintains separate read and write threads for each player
- Synchronizes player positions (x,y coordinates) in real-time
- 25ms update interval for position broadcasting

## Getting Started
1. Clone the repository:
```
git clone https://github.com/astrea25/Cops-vs-Robbers.git
```
2. Start the GameServer by running the main class:
```
java GameServer
```
3. Server will wait for 2 players to connect
4. Once both players are connected, the game automatically starts
5. Players will receive a "We now have 2 players. Go!" message when the game begins

## Network Protocol
- Player positions are transmitted as double values
- Each player receives the other player's x and y coordinates
- Data is transmitted using Java's DataInputStream and DataOutputStream

## Technical Requirements
- Java Runtime Environment
- Network connectivity between server and clients
- Port 45371 must be available on the server machine

## Error Handling
The server includes error handling for:
- IO Exceptions during server setup
- Connection handling
- Data transmission
- Thread interruptions
