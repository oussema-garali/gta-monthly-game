# Vice City Monthly - Multiplayer (40 players)

A real-time, GTA-inspired, corporate-friendly browser quiz for up to 60 players. One host creates a room and shares the website URL and six-character room code. Players join on their own phones or laptops. The host starts, reveals, and advances three missions. Scores update live (+100 per correct answer).

## Run locally

Requires Node.js 18+; no npm dependencies.

```bash
node server.js
```

Open http://localhost:3000 to create a room. **localhost only works on the host's computer**, so for 40 remote colleagues deploy this folder to an organization-approved Node.js hosting service that supports long-lived HTTP connections / Server-Sent Events, with `node server.js` as start command and `PORT` set by the platform.

Share the deployed HTTPS website URL and the room code in Teams. Host and players use the same website.

## Important

- Room and scores are stored **in server memory**, not a database. Restarting the server resets rooms. Use one server instance, no load balancing without shared state.
- There is no sign-in or anti-cheat, so use it for a fun icebreaker, not high-stakes scoring. Players can choose any display name.
- Do not enter sensitive or confidential data. Confirm hosting is approved by your IT policies.
- Host control is protected by a randomly generated token held in the host's browser memory. Keep the host tab open until the game finishes.
- For deployment beyond an internal icebreaker, add authentication, persistent storage, rate limits, TLS and proper operational monitoring.
