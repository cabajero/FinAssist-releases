# FinAssist

A private, local-first desktop app for tracking all your financial assets in **PLN** — with Polish **PIT-38** tax rules built in.

This repository holds the **released app** only. Download it from [Releases](../../releases).

## What it does

- **Interactive Brokers** — imports Activity Flex statements (file or automatic sync with a Flex token kept in the macOS Keychain): stocks, ETFs, options, dividends, withholding tax, corporate actions, cash.
- **Crypto** — imports transaction history (CSV) from Binance, Coinbase, Crypto.com (App and Exchange) and Revolut, or enter it by hand; live prices from Coinbase, Binance and Crypto.com.
- **Cash and real estate** — bank and savings balances per place; properties with purchase details, co-ownership share and dated valuations.
- **Savings plans** — IKE, IKZE, PPK, OFE and insurance policies (counted at their withdrawal value): contributions by you, your employer or the state, values from statements, and for IKE/IKZE the yearly limit with how much more you can pay in.
- **Live prices** — US stocks and ETFs from Yahoo Finance; NBP exchange rates.
- **Overview** — net worth, value over time, breakdown by asset class, currency and place, today's movers.
- **Performance** — time-weighted and money-weighted return, compared with the S&P 500 (total return, in PLN).
- **Income** — dividends and interest by month and by stock, with an estimate of the next 12 months.
- **Taxes (PIT-38)** — sections C (shares and options, FIFO, NBP rate of the day before), D (crypto) and G (foreign dividends), share losses from earlier years, CSV export for you or your accountant.
- **Backups** — daily automatic backup, folder of your choice, one-click restore. Light and dark mode.

## Install (macOS)

1. Download the `.dmg` from the [latest release](../../releases/latest) and open it.
2. Drag **FinAssist** to **Applications**.
3. The first time, **right-click FinAssist → Open → Open**. The app is signed ad hoc, not notarized by Apple, so macOS asks once. (Or: System Settings → Privacy & Security → *Open Anyway*.)

Requirements: macOS 11 or later. Built for Intel Macs; runs on Apple Silicon through Rosetta 2.

Check the download against `SHA256SUMS.txt` in the release: `shasum -a 256 FinAssist_<version>_x64.dmg`.

**Updating:** quit FinAssist, open the new `.dmg` and drag FinAssist to Applications again (replace). Your data stays where it is. Install releases in order of time — a newer database can't be opened by an older version.

## Your data

Everything stays on your Mac, in `~/Library/Application Support/com.finassist.app/` (a single SQLite database plus its backups). FinAssist has no account and no server. It only connects to:
- the IBKR Flex Web Service (only if you set up sync),
- the NBP API (exchange rates),
- Yahoo Finance, Coinbase, Binance and Crypto.com (prices — requests contain only tickers).

## Disclaimer

FinAssist's tax figures are **estimates** to check against your own records before filing; they are not tax advice. Rules for crypto and for deducting losses follow the PIT act as implemented in the app — confirm them with a tax advisor.
