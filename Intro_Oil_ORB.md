# Intro_Oil_ORB BrentCrudeOil
Vi ska undersöka olja och försöka bygga en new york opening range breakout. Till skillnad från tidigare strategier som utvecklats kommer denna handla på lägre tidsram(5-min). Denna strategi kommer utgå från att köpa när pris bryter ovanför opening range och sälja när pris bryter under. Eftersom entries och exits kommer ske baserat på high och lows, t.ex.
bullish_breakout = high > opening_high är det viktigt att entry_price är nästa bar open. I verklgiheten skulle priset vara opening_high men eftersom vi jobbar med csv data kan vi på de bars där både stop loss och take profits sker inte veta vilken som sker först. Vi sätter därför också att alla bars där sl och tp träffas samtidigt till automatisk sl. Med
dessa konservativa åtgärderna kan vi analysera resultaten mer realistiskt. För de tillfällen då både bullish_breakout = high > opening_high och bearish_breakout = low < opening_low
är sant blir det inga entries. Vi hypotiserar om att volatilitetsfilter kan gynna strategin och vi kör ett bastest på vårat in sample (2011-2019) här för att se om någon som helst edge finns innan vi börjar arbete på det. Vi sätter stop loss vid motsatt sida av opening range, och tp på 2rr med dessa kostnader "fixed_spread_ticks": 1.0, "slippage_ticks": 1.0, "commission_usd_per_side": 2.5.
--- STATS ---
Market: Brent Crude Oil (5min)
Trades: 1772
Total PnL (USD): 39685.0010
Gross Profit (USD): 643729.0000
Gross Loss (USD): -604043.9990
Profit Factor: 1.0657
Winrate: 0.3386
Avg Win (USD): 1072.8817
Avg Loss (USD): -515.3959
Expectancy (USD/trade): 22.3956
Max Drawdown (USD): 19271.0000
Max Losing Streak (trades): 16
Sharpe (trade-level): 1.0589
Vi går in i projektloggen och börjar arbete på denna strategi nu.
