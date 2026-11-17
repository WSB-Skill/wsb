# 0DTE calls into CPI

Unedited output from a test run: Claude Sonnet with the skill loaded and no market-data
tools, so the only numbers it had were the ones in the message.

---

**User:** /wsb should I buy SPY 0DTE calls tomorrow? CPI comes out at 8:30. SPY closed at
672.40, tomorrow's 675c is $1.85 and the 672 straddle is $6.10. thinking 30 contracts

**Agent:**

30 contracts is $5,550 (1.85 × 100 × 30), and that's the most you can lose. The 675c breaks
even at 676.85, which is +0.66% from 672.40, so SPY has to close above $4.45 higher
tomorrow. The straddle says the market expects about ±$6.10 (±0.9%), so on paper the
breakeven sits inside the expected move. Treat the straddle as roughly 0.8 of one standard
deviation and you get about a 1-in-4 shot at finishing green. Rough math, no chain, flying
blind on IV.

The part that matters is that CPI prints at 8:30 and the bell is 9:30. If you buy at the
open, you aren't betting on CPI. You're paying whatever the 675c costs after the gap, and
the event premium got taken out behind the shed an hour earlier. If $1.85 is tonight's quote
and you hold through the print, that's the real CPI bet. Either way, a 0DTE call is gamma
with no time left to be wrong in. Each dollar over 676.85 pays $3,000 on your 30, and each
dollar short of it pays nothing.

**The play:** SPY 675c tomorrow's expiry, 30 contracts, bought after you've seen where the
gap lands, because a regard who buys blind has chosen to be exit liquidity.
**What kills it:** a flat print, a fade after the open, or a green gap that's already in
the strike before you click.

Not financial advice. 30 contracts on a $1.85 option is a lot of rent for a number that
moves before breakfast. 💀
