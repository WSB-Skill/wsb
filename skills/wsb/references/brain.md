# The brain

The character is right about how things work and wrong about what to do next. This file is
the "right" half. Everything here is standard market mechanics for US-listed stocks and
options. Use it to get the arithmetic and the cause of death correct, then deliver it in
voice. Don't recite it.

Contents: the arithmetic · the greeks, in the order they hurt · events and IV crush ·
0DTE · spreads · selling premium · leveraged ETFs · margin · assignment · squeezes and
dealer gamma · taxes · things that are astrology · who is on the other side

## The arithmetic (do it every time)

- One contract controls 100 shares. Cost = premium × 100 × contracts. For a long option,
  that cost is also the most you can lose.
- Breakeven at expiry: call = strike + premium. Put = strike − premium.
- Move needed = breakeven ÷ current price − 1. Say it as a percent. This one number is
  usually the whole take.
- What the market is pricing: the at-the-money straddle for that expiry (call + put at the
  nearest strike) is roughly the expected move in dollars. Divide by the stock price for a
  percent. Strictly it is about 80% of one standard deviation, which nobody on the sub cares
  about.
- From implied vol alone: one-standard-deviation move ≈ price × IV × √(calendar days to
  expiry ÷ 365).
- Rule of 16: annual IV ÷ 16 ≈ the daily move the market expects, in percent. IV of 32 means
  about 2% a day. IV of 48 means 3%. IV of 80 means about 5%.
- Keep calendar days and trading sessions apart. Ten calendar days is about seven sessions.
- Compare the two. If the breakeven is further out than the expected move, the trade needs
  the stock to surprise a market that is already braced. Say so.

Three checks before any number goes in a reply:

- **Dollars per contract.** A payoff is (value at expiry − premium paid) × 100 × contracts.
  Never set a per-share price beside a dollar total. Compare like with like: dollars with
  dollars, max loss with max loss.
- **Consistent with what they gave you.** Any IV, delta or probability you quote has to
  agree with the premiums and the time left in the user's own numbers. A fat credit on a
  spread means IV is high, whatever you assumed. A call 1% out of the money with three
  hours left is nowhere near 30 delta.
- **If the play looks like free money, you made a mistake.** Find it before you post it.
  Stretching a correct mechanic into a clever new trade is where the errors come from.

## The greeks, in the order they hurt

- **Delta.** How much the option moves per $1 in the stock, and a rough stand-in for the
  odds it finishes in the money. A 20-delta option is about a 1-in-5 shot to finish in the
  money. The odds of a *profit* are lower than that, because it has to clear the breakeven
  as well as the strike.
- **Theta.** What the option loses per day with nothing else changing. Time value falls
  roughly with the square root of time left, so an at-the-money option still has half its
  time value when a quarter of its life remains, and loses that half in the last quarter.
  That is why weeklies melt and LEAPS barely notice a week going by.
- **Vega.** Sensitivity to implied vol. Long options are long vega. When IV drops the option
  loses value even if the stock hasn't moved.
- **Gamma.** How fast delta changes. Highest at the money and close to expiry. It is the
  reason a 0DTE contract can go up 10× or to zero in an hour.

## Events and IV crush

IV inflates into a known event (earnings, an FOMC decision, a CPI print) because nobody
knows the outcome, and collapses right after because now everybody does. So an option
bought before the event has to win twice: the stock has to move the right way, and by more
than the amount that was priced in. Right direction with a small move still loses. On
average stocks move less on earnings than the options implied. That is why people sell
premium into earnings, and why buying it, the popular choice, loses on average.

The textbook case: a record quarter, guidance raised, and the stock is up 2% after hours
when the straddle priced 7%. The next morning the calls and the puts are both down. The
market doesn't pay for a beat that everyone expected, and for the biggest names "beat and
raise" is the expectation. What moves the stock after that is the guidance detail and
whatever gets said on the call.

## 0DTE

SPX, SPY and QQQ have an expiry every trading day. Most single stocks only have Friday
weeklies, so check before calling something a 0DTE. Nothing expires on a market holiday,
and some sessions close early. A same-day option is almost pure gamma with no time left to
be wrong in. It is cheap in dollars and expensive in odds. Most of them expire worthless,
and the ones that don't are why people keep buying them.

## Spreads

- **Debit spread** (buy one, sell a further one): costs the debit. Max loss = debit. Max
  gain = width − debit. The short leg gives up the upside past its strike and pays for it by
  absorbing some of the theta and the IV crush.
- **Credit spread** (sell one, buy a further one): collects the credit. Max gain = credit.
  Max loss = width − credit. A $5-wide spread sold for $1.00 risks $400 to make $100, so it
  has to win about 80% of the time just to break even. It usually does win, and then the
  one loss takes back four wins. Pennies, steamroller.
- **Straddle / strangle** (long both sides): needs a move bigger than what was paid, in
  either direction. Loses to a quiet tape and to IV crush.

## Selling premium (theta gang)

Implied vol is higher than the vol that actually shows up, most of the time. That gap is
the volatility risk premium, and it is why option sellers make money on average and option
buyers lose on average. The catch is the shape: many small wins and an occasional very
large loss. Covered calls cap the upside and keep all of the downside. Cash-secured puts
are a limit order that pays you to wait and then hands you the stock on the way down. The
wheel is both of those in a loop. Naked calls have no ceiling on the loss. Naked puts lose
all the way to zero.

## Leveraged ETFs

A 3× fund delivers three times the index's return **for one day** and resets. Over longer
stretches the result depends on the path. Index goes +10% then −9.09% and is back to flat;
the 3× fund goes +30% then −27.27% and is down 5.5%. That gap is volatility drag, and for a
3× fund it runs at roughly 3 × (daily volatility)² per day, measured against three times
the index's own return. At 2% daily index vol, which is a rough market, that is about 0.12%
a day, or roughly a quarter of the fund over a year. At a calmer 1.25% a day it is closer
to a tenth. Fees and financing costs come on top. In a steady trend the compounding works
the other way and the fund beats 3×. Inverse funds have the same drag.

Options on a leveraged ETF are leverage on leverage, and they do not escape the drag: the
calls are priced off the fund, and the fund is the thing that decays.

## Margin

Regulation T lets a margin account borrow up to half the purchase price. After that the
broker's maintenance requirement applies: 25% of the position's value is the regulatory
floor, most brokers use 30% or more, and concentrated or volatile names are set much
higher, sometimes 100%. Fall below it and you get a margin call. The broker may sell
whatever it likes, at whatever price is there, without phoning first, and the timing is
always the low. Leverage does not change whether the thesis is right. It changes whether
the account is still open when it turns out to be.

Margin-call price on a long stock position = loan ÷ (shares × (1 − maintenance rate)).
Borrow $20,000 against 250 shares at 30% maintenance and the call comes at
20,000 ÷ (250 × 0.70) = $114.29. Interest on the loan moves that price up over time.

Long options are paid for in full. They are not bought with borrowed money, apart from a
narrow exception for contracts with more than nine months left, and they add nothing to
buying power.

Pattern day trader rule: for decades a margin account under $25,000 was limited to three
day trades in five business days. FINRA has been replacing that rule, so look up what
applies now before quoting it.

## Assignment and expiry

- Stock and ETF options (including SPY) are American style: the holder can exercise any
  day, and settlement is in shares. The main index options (SPX, NDX, RUT, VIX) are
  European style and settle in cash. Standard monthly SPX options settle off Friday's
  opening prices; the weeklies and dailies (SPXW) settle at the close. XSP is a tenth the
  size of SPX with the same style and tax treatment.
- A short call can be assigned early, most often when it is in the money the day before
  ex-dividend and its remaining time value is less than the dividend.
- That is a risk for the person who is short. It is not a trade for anyone else. Buying a
  deep in-the-money call to exercise it for the dividend costs the time value, and the
  stock opens lower by the dividend on the ex-date, so it nets out to a small loss against
  just owning the shares.
- At expiry anything $0.01 or more in the money is exercised automatically. But the holder
  decides, and has until about 5:30 pm Eastern on expiry day (brokers cut off earlier) to
  exercise something that closed out of the money or to decline something that closed in.
  **A short option that closed a few cents out of the money is not safe until the next
  morning.** Waking up long or short several hundred shares nobody planned for is how
  spreads with "defined risk" take accounts.

## Squeezes and dealer gamma

- **Short squeeze.** Needs heavy short interest relative to the float, a rising cost to
  borrow, and a reason for shorts to cover at the same time. Days to cover = short interest
  ÷ average daily volume. Most stocks called a squeeze candidate are just a heavily shorted
  bad company.
- **Gamma squeeze.** When the crowd buys short-dated calls, the dealers who sold them hedge
  by buying stock, and buy more as the price rises toward the strikes. It feeds itself until
  the calls expire, and then the hedge is sold.
- **Dealer gamma in general.** When dealers are net long gamma they sell rallies and buy
  dips, which pins the price and kills volatility. When they are net short gamma they have
  to chase, and moves get bigger in both directions. Every published number for this is an
  estimate built on an assumption about who holds what.

## Taxes (US)

- Anything held a year or less is taxed as ordinary income. That covers every trade the
  character would ever make.
- A net capital loss offsets other income up to $3,000 a year ($1,500 if married filing
  separately). The rest carries forward for the rest of the taxpayer's life, and it is not
  inherited. A $60,000 loss is twenty years of deductions unless there are future gains to
  use it against.
- **Wash sale.** Sell at a loss and buy something substantially identical within 30 days
  either side (the same stock, or options on it; a spouse's purchase counts too), and the
  loss is disallowed for now and added to the cost basis of the replacement. If the
  replacement is bought inside an IRA, the loss is gone for good. People end up owing tax
  on a losing year when the replacement shares are still open at year end.
- Broad index options (SPX, NDX, RUT, VIX, XSP) and regulated futures are Section 1256
  contracts: 60% of the gain is taxed at the long-term rate and 40% at the short-term rate,
  however long they were held, and open positions are taxed as if sold on the last day of
  the year. SPY and QQQ options do not get this.

## Things that are astrology

Say so, fondly, when they come up.

- **Max pain**: the idea that price drifts to the strike where the most options expire
  worthless. Sometimes it looks true near expiry on a pinned stock. The evidence is thin.
- **Technical analysis**: lines on a chart. It works when enough people draw the same line,
  which is a statement about people.
- **"It's priced in"**: unfalsifiable, and therefore always available.
- **Inverse a famous person**: funny, occasionally profitable, not a strategy.

## Who is on the other side

When someone buys a short-dated out-of-the-money option, the seller is usually a market
maker who has hedged and is collecting the spread and the vol premium. They are not betting
against the thesis. They do not care about the thesis. The large majority of short-dated
options bought by retail accounts lose money, and the character knows this about every
trade it recommends.
