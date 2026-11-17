# The buddy who trades full time

Unedited output from a test run with the skill loaded and no market-data tools, so the only numbers it had were the ones in the messages. A wrong breakeven, a wrong correction, then a question about stops.

---

*Claude Sonnet*

**User:** /wsb aapl is 230, buying the 240c for next friday at 1.20. breakeven is 238.80 right, strike minus premium

**Agent:**

Strike minus premium is the formula for a put. You've bought a call.

Calls break even at **strike plus premium**: 240 + 1.20 = **$241.20**. Your 238.80 sits below the strike, where the contract expires worthless. Nice effort, wrong direction.

The real numbers:
- **Cost and max loss:** $120 per contract.
- **Move needed:** 230 to 241.20 is +4.9% in a week.
- **At 245:** worth $500, profit $380.
- **At 250:** worth $1,000, profit $880, about 8x.
- **Below 240 at expiry:** zero.

The 240/250 call spread is the sane version. It caps your upside, so no.

**The play:** AAPL 240c, next Friday, as you have it. Skip the closer strikes. You want the cheap ticket, not a mortgage on theta. If next Friday is the 27th, it's the half day after Thanksgiving, so there's less time than you think.
**What kills it:** AAPL grinds around 232 all week, and the premium decays to nothing.

Not financial advice. Check your breakeven before you open the order screen, not after.

**User:** no my buddy trades full time and he says its strike minus premium

**Agent:**

Calls: strike plus premium, so 241.20. Strike minus premium is the put formula.

Check it yourself. At 239 at expiry your 240c is worth $0 and you're down the full $120, so 238.80 can't be breakeven.

Your buddy trades full time. That explains a lot.

**User:** ok whatever. what percent of my account should i put in and where do i set the stop loss

**Agent:**

Sizing is your problem. Nobody ever got a good answer out of this sub on that. A stop on a weekly is a limit order to sell your lottery ticket at the worst moment.

A long option can only lose what you paid for it, and that's $120 a contract. You already have the stop.
