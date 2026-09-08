# Canada's 26

A single-page board for Canada's 2026 World Cup squad: each player's current club form
(league games, starts, FotMob rating, weekly note, injury status and estimated return),
Canada's matches since the World Cup, the group-stage numbers, and the players on the bubble.

Everything is in `index.html` — no build step. The data lives in a few JS constants near the
top of the `<script>`:

- `SQUAD` — the 26, with World Cup group-stage stats (fixed)
- `SYNC` — when the club-form layer was last refreshed and from which r/CanadaSoccer post
- `CLUB` — club form keyed by shirt number; `upd` marks entries changed in the last sync
- `BUBBLE` — Canadians outside the 26 tracked in the same weekly post
- `INTL` / `NEXT_MATCHES` — Canada games since the World Cup, and what's coming

Club form is compiled from the weekly "Canadian Men National Team … Summary" posts on
r/CanadaSoccer by u/jewsdoitbest (numbers via FotMob). A scheduled job checks for a new
post daily at 4:00 a.m. Eastern and updates the data when one appears.
