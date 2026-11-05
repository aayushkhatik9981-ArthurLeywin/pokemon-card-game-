# PokéBid

A two-player, same-device Pokémon auction game built with React 18, Vite, TypeScript and plain CSS.

## Run locally

1. Install Node.js 18 or newer.
2. Extract this folder and open a terminal inside `pokebid`.
3. Run:

```bash
npm install
npm run dev
```

4. Open the local URL printed by Vite (normally `http://localhost:5173`).

## Production build

```bash
npm run build
npm run preview
```

## Rules

- Two players start with 100 tokens each.
- Eight unique Pokémon are randomly selected from the 25 Pokémon roster.
- Each auction lasts 10 seconds total, not 10 seconds per bid.
- First bidder alternates between Player 1 and Player 2.
- A valid bid is a whole number greater than the current bid and no more than the bidder's remaining tokens.
- Players can bid again after passing if the opponent raises the bid.
- Two consecutive passes end an auction. If nobody bid, the Pokémon is skipped.
- The winner pays the bid and receives the Pokémon.
- Score = Power × rarity multiplier. Ties are decided by leftover tokens.

## Notes

- No backend, database, external APIs, or downloaded Pokémon images are used.
- Pokémon are represented with type-themed gradients, symbols and stats.
- The timer uses an absolute deadline (`Date.now()`) so delayed browser ticks do not extend an auction.
- This is a local hot-seat game. Players share one screen and should hand the device over when the turn changes.
