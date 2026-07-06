<div align="center">

<img src="https://capsule-render.vercel.app/api?type=venom&height=200&color=gradient&customColorList=12&text=FD-SERVER&fontSize=80&fontColor=fff&animation=twinkling&desc=Multiplayer+Relay+for+Frisian+Draughts&descSize=17&descAlignY=65&stroke=FFFFFF&strokeWidth=1" alt="FD-Server Banner" />

<img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&size=19&pause=1000&color=00D9FF&center=true&width=900&height=50&lines=Raw+TCP+sockets+%C2%B7+White%2FBlack%2FSpectator+%C2%B7+plain-text+protocol" alt="Typing SVG" />

<br>

[![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white&labelColor=0D1117)](https://openjdk.org)
[![Fly.io](https://img.shields.io/badge/Fly.io-8B5CF6?style=for-the-badge&labelColor=0D1117)](https://fly.io)

</div>

<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" width="100%">

### What it is

The multiplayer backend for [Frisia](https://github.com/NoamFav/Frisia) (Frisian Draughts). A plain Java `ServerSocket` accepts connections, assigns each client a role — `White`, `Black`, or `Spectator` — and relays a small plain-text protocol between them: `MOVE`, `CHAT`, `READY`, `RESIGN`, `DRAW`, `DISCONNECT`. Deployed on Fly.io.

### Protocol

| Command | Effect |
|---------|--------|
| `READY` | Announces the player has joined; broadcasts role to the room |
| `MOVE x,y TO x,y` | Relays a move to the opponent |
| `CHAT <msg>` | Broadcasts a chat message to everyone else |
| `RESIGN` / `DRAW` | Broadcasts the game-ending event |
| `DISCONNECT` | Closes the connection cleanly |

### Running it

```sh
git clone https://github.com/NoamFav/FD-Server && cd FD-Server
mvn compile exec:java -Dexec.mainClass="com.server.MainServer"
# or via Docker
docker build -t fd-server . && docker run -p 9000:9000 fd-server
```

<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" width="100%">

<div align="center">
Made with ♥ by <a href="https://github.com/NoamFav">NoamFav</a>
<img src="https://capsule-render.vercel.app/api?type=waving&height=90&color=gradient&customColorList=12&section=footer" />
</div>
