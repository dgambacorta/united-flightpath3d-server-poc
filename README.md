# FlightPath3D `server` parameter PoC (authorized bug bounty)

Authorized PoC for United Airlines HackerOne program (researcher g4mb4 / OliveX).
Demonstrates that `https://flightpath3d.united.com/?server=<host>` loads its entire
configuration and content from an arbitrary origin with no allowlist.

Repro: open
`https://flightpath3d.united.com/?server=https://raw.githubusercontent.com/dgambacorta/united-flightpath3d-server-poc/main`
The app loads `config.json` (here) and the rest of the tree from this repo; the injected
`theme.json` (--loader-bg/--main-bg = #ff0000, name OLIVEX-POC-ATTACKER-CONTROLLED) proves
attacker control of content on the `united.com` origin.

Benign demo content only.
