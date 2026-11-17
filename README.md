# WSB-Skill

I was tired of Claude being logical about my trades. Every time I asked about weeklies it
wanted to talk about position sizing. So I made a skill that turns it into as much of a
degenerate as I am. It finally speaks a language I understand, and it is supportive of my
casino habits.

`/wsb` makes your agent talk and think like an r/wallstreetbets regular. It still does the
math. It just doesn't let the math change anything.

```
> /wsb NVDA reports Wednesday. Stock's at 140, the 150c expiring Friday is $2.10,
  ATM straddle is about $11. Thoughts?

Straddle says ±7.9%. Your 150c breaks even at 152.10, which is +8.6%. So the stock has
to beat the move the market already priced in before you've made a dollar, and Thursday
morning IV gets taken out behind the shed whether you were right or not.

Everyone buying that strike knows this. That's why it's $2.10.

The play: the 150c, obviously, you'd already decided. The version that can pay is the
140/150 call spread: about $3.40, breaks even at +2.4%, and the short leg eats most of
the crush. Nobody has ever posted a call spread to the front page though.
What kills it: a good quarter and a 5% pop. So, the usual outcome.

Not financial advice. I'm a language model. I can't even get a Robinhood account, and
they give those to anyone.
```

More in [`examples/`](examples/).

## How it works

Two rules, and the joke is the gap between them.

1. **The analysis is real.** Breakevens, implied moves, theta, IV crush, leveraged-ETF
   decay, wash sales. The numbers are right, or it says it doesn't have them. It won't make
   up a price.
2. **The risk management is absent.** No position sizing, no stop losses, no "consider
   speaking to a financial advisor". It tells you exactly how the trade dies and then
   tells you to take it.

It can roast a portfolio, rate a YOLO, do the forensics on your loss porn, say "congrats
and fuck you" to your gains, write a DD with your real position in it, explain a put credit
spread like you're regarded, and answer questions that have nothing to do with money as if
they were trades.

## Install

A skill is a folder with a `SKILL.md` in it. Put the folder where your agent looks for
skills and you're done.

**Claude Code, as a personal skill** (gives you the short `/wsb` command):

```bash
git clone https://github.com/WSB-Skill/wsb.git
cp -r wsb/skills/wsb ~/.claude/skills/
```

On Windows PowerShell:

```powershell
git clone https://github.com/WSB-Skill/wsb.git
Copy-Item -Recurse wsb\skills\wsb "$HOME\.claude\skills\wsb"
```

**Claude Code, as a plugin** (the command is `/wsb-skill:wsb`):

```
/plugin marketplace add WSB-Skill/wsb
/plugin install wsb-skill@wsb-skill
```

**Claude apps (web and desktop):** zip the `skills/wsb` folder so that `wsb/` is the top
level of the zip, then upload it in the Skills section of your settings.

**Anything else:** `SKILL.md` follows the open [Agent Skills](https://agentskills.io)
format. If your agent doesn't read skills, paste `skills/wsb/SKILL.md` and the three files
in `references/` into its system prompt.

## Use

```
/wsb calls or puts on TSLA this week
/wsb roast my portfolio: 60% VOO, 20% AAPL, 10% cash, 10% NVDA LEAPS
/wsb down 62k on puts this week, rate my loss
/wsb write me a DD for my AMD calls, I hold 12 of the Dec 180c
/wsb explain IV crush like I'm regarded
```

Or just say "wsb mode" or "talk like wallstreetbets". It stays in character until you tell
it to stop.

It gets better with live data. If your agent has web search or a market-data tool, the
skill tells it to look up the price, the premium, and the earnings date before it opens its
mouth. If it has nothing, it works from the numbers you give it and asks you to post the
chain.

## What it won't do

There are no guard rails on risk. There are a few on everything else, and the sub has the
same ones.

- **It won't touch your money.** If your agent is wired to a brokerage it still won't place,
  change, or cancel an order. It's the ideas guy. You press buy.
- **It won't make up numbers.** Jokes can be absurd. Prices, dates, and filings are real or
  marked unknown.
- **It won't help with pump and dumps,** fake screenshots, or penny-stock shilling.
- **It uses "regarded",** the way the sub spells it now, and skips the slurs that word
  replaced.
- **It drops the act when someone is really in trouble.** A person who has stopped joking
  gets a straight, decent answer. The top comments on the worst loss posts do the same.
- **It stops when you tell it to.**

## What's in the repo

```
skills/wsb/
  SKILL.md                 the persona: the two rules, the voice, when the bit stops
  references/
    brain.md               the part that's right: option math, greeks, margin, taxes
    lexicon.md             vocabulary, nicknames, lore, and what marks a tourist
    formats.md             DD, YOLO, loss and gain replies, portfolio roast
examples/                  sample conversations
.claude-plugin/            lets Claude Code install the repo as a plugin
```

## Contributing

PRs welcome, especially:

- current slang and memes (the lexicon goes stale quickly)
- corrections to anything in `brain.md` (if the math is wrong the whole joke is dead)
- good sample conversations for `examples/`

Keep `SKILL.md` short. Detail belongs in `references/`.

## Disclaimer

This is a comedy persona. Nothing it says is financial advice, investment advice, or a
recommendation to buy or sell anything. It is a language model doing an impression of
people who lose money on purpose. Most short-dated options expire worthless, and the skill
will tell you so right before it tells you to buy them. If you trade on what it says, that
was your decision and your money.

Not affiliated with Reddit, r/wallstreetbets, or Anthropic.

## License

MIT
