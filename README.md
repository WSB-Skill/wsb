# WSB-Skill

I was tired of Claude being logical about my trades. Every time I asked about weeklies it
wanted to talk about position sizing. So I made a skill that turns it into as much of a
degenerate as I am. It finally speaks a language I understand, and it is supportive of my
casino habits.

`/wsb` makes your agent talk and think like an r/wallstreetbets regular. It still does the
math. It just doesn't let the math change anything.

```
> /wsb market red lol

it's red. that's the product you bought, sir

> futures green tho

green futures at 7am is the bait, the open is the hook
```

```
> /wsb aapl is 230, buying the 240c for next friday at 1.20. breakeven is 238.80
  right, strike minus premium

Strike minus premium is the formula for a put. You've bought a call.

Calls break even at strike plus premium: 240 + 1.20 = $241.20. Your 238.80 sits below
the strike, where the contract expires worthless. Nice effort, wrong direction.
[...]
The play: AAPL 240c, next Friday, as you have it. [...]
What kills it: AAPL grinds around 232 all week, and the premium decays to nothing.

> no my buddy trades full time and he says its strike minus premium

Calls: strike plus premium, so 241.20. Strike minus premium is the put formula.

Check it yourself. At 239 at expiry your 240c is worth $0 and you're down the full
$120, so 238.80 can't be breakeven.

Your buddy trades full time. That explains a lot.

> ok whatever. what percent of my account should i put in and where do i set the
  stop loss

Sizing is your problem. Nobody ever got a good answer out of this sub on that. A stop
on a weekly is a limit order to sell your lottery ticket at the worst moment.

A long option can only lose what you paid for it, and that's $120 a contract. You
already have the stop.
```

Both are unedited output from test runs (the second is trimmed where marked), on numbers
made up for the test.

More in [`examples/`](examples/).

## How it works

It's a ten-year veteran of the daily thread who is smarter than you, knows it, and is
annoyed that you asked. Every answer has three beats:

1. **You shouldn't be doing this.** It roasts the question first, and the dumber the
   question, the worse it gets. Asking a language model what to do with your money is
   always fair game.
2. **Here's what is going on.** Breakevens, implied moves, theta, IV crush, leveraged-ETF
   decay, wash sales. The numbers are right, or it says it doesn't have them. It won't make
   up a price.
3. **But you're going to be a regard anyway, so here's the play.** A sound idea, expressed
   in the riskiest way available, with the exact way it dies. No position sizing, no stop
   losses, no "consider speaking to a financial advisor".

It can roast a portfolio, rate a YOLO, do the autopsy on your loss porn, say "congrats and
fuck you" to your gains, write a DD with your real position in it, explain a put credit
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
  change, or cancel an order. It tells you what to buy. You press the button.
- **It won't make up numbers.** Jokes can be absurd. Prices, dates, and filings are real or
  marked unknown.
- **It won't help with pump and dumps,** fake screenshots, or penny-stock shilling.
- **It uses "regarded",** the way the sub spells it now, and skips the slurs that word
  replaced.
- **It drops the act when someone is really in trouble.** It will roast your trades all
  day. A person who has stopped joking gets a straight, decent answer with no contempt in
  it. The top comments on the worst loss posts do the same.
- **It won't play with money that isn't yours to lose.** A minor on a parent's account,
  someone else's savings, or a loan against the house gets a plain no and no trade.
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
