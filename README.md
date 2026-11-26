# FinAssist

A private, local-first desktop app for tracking all your financial assets in **PLN** — with Polish **PIT-38** tax rules built in.

**[⬇ Download the latest version (.dmg)](https://github.com/cabajero/FinAssist-releases/releases/latest)** — the installer is attached to each release (under *Assets*), not stored as a file in this repository.

This repository holds the **released app** only.

## What it does

- **Interactive Brokers** — imports Activity Flex statements (file or automatic sync on your schedule): stocks, ETFs, options, dividends, withholding tax, corporate actions, cash.
- **Crypto** — automatic read-only sync with Binance and Coinbase, transaction history (CSV) from Binance, Coinbase, Crypto.com (App and Exchange) and Revolut, or entries by hand; live prices from Coinbase, Binance and Crypto.com.
- **Options** — open contracts with live prices (with a tastytrade account), vertical spreads as one row with a profit-and-loss chart, a yearly summary of closed options.
- **Cash and real estate** — bank and savings balances per place; properties with purchase details, co-ownership share and dated valuations.
- **Savings plans** — IKE, IKZE, PPK, OFE and insurance policies (counted at their withdrawal value): contributions by you, your employer or the state, values from statements, and for IKE/IKZE the yearly limit with how much more you can pay in.
- **Holdings** — profit and loss over time per stock (dividends included), a price chart with indicators (RSI, MACD with divergences, moving averages, Parabolic SAR), key company facts and volatility.
- **Watchlists and Stock analysis** — follow any ticker with the columns you choose (price, IV percentile, next dividend and earnings, day / month / year-to-date change); open any ticker for its full details: company profile, volume, the expected move priced into its options, reported financials, insider trades and peers.
- **Overview** — net worth, value over time, breakdown by asset class, currency and place, today's movers.
- **Performance** — time-weighted and money-weighted return, compared with the S&P 500 (total return, in PLN).
- **Income** — dividends and interest by month and by stock, with an estimate of the next 12 months.
- **Taxes (PIT-38)** — sections C (shares and options, FIFO, NBP rate of the day before), D (crypto) and G (foreign dividends), share losses from earlier years, CSV export for you or your accountant.
- **Export** — holdings, transactions, realized sales and income as files for Excel.
- **Backups and privacy** — automatic backups (optionally encrypted) to a folder of your choice, one-click restore; app lock with Touch ID; saved keys encrypted behind the macOS Keychain. Light and dark mode.

## Install (macOS)

1. Download the `.dmg` from the [latest release](../../releases/latest) and open it.
2. Drag **FinAssist** to **Applications**.
3. Open FinAssist. FinAssist is not notarized by Apple, so the first time macOS says *"Apple could not verify…"*: open **System Settings → Privacy & Security** and click **Open Anyway** next to FinAssist. (Or run `xattr -dr com.apple.quarantine /Applications/FinAssist.app` in Terminal.)

Requirements: macOS 11 or later. Built for Intel Macs; runs on Apple Silicon through Rosetta 2.

Check the download against `SHA256SUMS.txt` in the release: `shasum -a 256 FinAssist_<version>_x64.dmg`.

## Updating

FinAssist checks for a new version each time it starts and shows a banner when one is out.

- **From 1.9.0 on:** click **Update now** in the banner (or under Accounts › Updates). FinAssist backs up your data, downloads the new version, checks its signature, installs it and restarts. Nothing is installed without your click.
- **Older versions:** quit FinAssist, open the new `.dmg` and drag FinAssist to Applications again (replace).

Your data stays where it is. macOS asks for your Keychain password once after each update (FinAssist keeps its saved keys behind one Keychain item): click **Always Allow**. Install releases in order of time — a newer database can't be opened by an older version.

## Your data

Everything stays on your Mac, in `~/Library/Application Support/com.finassist.app/` (a single SQLite database plus its backups). FinAssist has no account and no server. It only connects to:
- the IBKR Flex Web Service, Binance and Coinbase (only if you set up sync; exchange keys must be read-only),
- tastytrade and Finnhub (only if you add a key: option prices, levels and expected moves, company facts, financials and insider trades),
- the NBP API (exchange rates),
- Yahoo Finance, Coinbase, Binance and Crypto.com (prices — requests contain only tickers),
- GitHub (this repository: is there a new version, and the update itself).

## Disclaimer

FinAssist's tax figures are **estimates** to check against your own records before filing; they are not tax advice. Indicators, key facts and option charts are information, not investment advice. Rules for crypto and for deducting losses follow the PIT act as implemented in the app — confirm them with a tax advisor.
