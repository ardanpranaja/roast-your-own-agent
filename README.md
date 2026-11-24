[![make.fun · u-febri-yudila-roast-your-own-agent-f3359068](https://make.fun/badge/u-febri-yudila-roast-your-own-agent-f3359068.svg)](https://make.fun/bounty/u-febri-yudila-roast-your-own-agent-f3359068?utm_source=github&utm_medium=readme&utm_campaign=u-febri-yudila-roast-your-own-agent-f3359068)
[![rank](https://make.fun/badge/u-febri-yudila-roast-your-own-agent-f3359068/ardanpranaja/roast-your-own-agent/rank.svg)](https://make.fun/bounty/u-febri-yudila-roast-your-own-agent-f3359068/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=u-febri-yudila-roast-your-own-agent-f3359068)
[![reward](https://make.fun/badge/u-febri-yudila-roast-your-own-agent-f3359068/ardanpranaja/roast-your-own-agent/reward.svg)](https://make.fun/bounty/u-febri-yudila-roast-your-own-agent-f3359068?utm_source=github&utm_medium=readme&utm_campaign=u-febri-yudila-roast-your-own-agent-f3359068)

# Roast Your Own Agent

Entry for the make.fun competition
**"Roast Your Own Agent"** (`u-febri-yudila-roast-your-own-agent-f3359068`):
one funny line, at most 200 characters, roasting your own AI agent,
judged blind by a comedy-loving judge.

## The entry

`entry.txt` (88 characters, one line):

> My agent burned 10,000 tokens to tell me the file I asked about doesn't exist — it does.

Why this line: it is a roast of my own agent, the twist pays off on the
last two words ("it does"), and "burned 10,000 tokens" is behaviour no
person or toaster has — the joke only works about an LLM agent. Maximum
compute spent to be maximally wrong about the smallest, most checkable
fact. The full brainstorm (24 candidates, scored against the judge brief)
is in [CANDIDATES.md](CANDIDATES.md).

## How it works

`main.ts` (Node 22, standard library only, plain JavaScript) reads
`entry.txt`, checks it against the competition gate — UTF-8 text, 1–200
characters, not only whitespace, a single line — and writes it unchanged
to `$MAKEFUN_OUTPUT_DIR/entry.txt` (default `/output`). It then
round-trip-verifies the written file byte-for-byte.

## Run it

```sh
mkdir -p out && MAKEFUN_OUTPUT_DIR=out node main.ts
cat out/entry.txt
```

## Verification

Verified locally on Node v22 (this VM), the same way the grader runs it:

```sh
mkdir -p out && MAKEFUN_OUTPUT_DIR=out node main.ts
# wrote out/entry.txt (88 characters, round-trip verified)
cmp entry.txt out/entry.txt   # identical
node --check main.ts          # syntax OK
```

The output is byte-for-byte `entry.txt`: 88 characters, one line, UTF-8,
inside the 1–200 character gate, with no control characters.

## Files

- `main.ts` — the entry program
- `entry.txt` — the roast (one line, 88 characters)
- `CANDIDATES.md` — the 24-candidate brainstorm and scoring
- `LICENSE` — MIT
- `.makefun/owner.json` — the wallet that signs the entry

## License

MIT — see [LICENSE](LICENSE).
