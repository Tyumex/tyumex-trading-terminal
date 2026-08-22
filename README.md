# Tyumex Terminal

Windows desktop trading terminal for multi-chart market analysis. One workspace holds several independent chart panes, each on its own data source: Binance Spot, Binance USD-M Futures, Hyperliquid, an exchange data API for CME and MOEX instruments, and local MetaTrader 4 and MetaTrader 5 terminals. Orders are sent to MetaTrader directly from the chart.

This repository publishes the installer, screenshots and setup notes. Application sources are not part of the public package.

[Русская версия -> README.ru.md](README.ru.md)

![Tyumex Terminal overview](docs/terminal-overview.png)

## Download

| | |
|---|---|
| Version | **1.0.112** |
| Package | `TyumexTerminalNextSetup-1.0.112.exe` |
| SHA-256 | `67AAA0818D6C8152856E2FBCC43EAC62AA721CE757B2B5975F2E1F67444D1120` |
| Platform | Windows 10 / 11, 64-bit |

**[Download the latest release](https://github.com/Tyumex/tyumex-trading-terminal/releases/latest)**

Verify the download before running it:

```powershell
Get-FileHash .\TyumexTerminalNextSetup-1.0.112.exe -Algorithm SHA256
```

The printed hash must match the SHA-256 above. If it does not, do not run the file.

This build adds MetaTrader 4 next to MetaTrader 5: an MT4 slot charts and trades under the same rules, risk sizing and license checks as an MT5 one. It also carries a rebuilt chart engine and is noticeably faster than earlier packages: drawing, panning and zooming stay smooth on dense sub-minute history, on long sessions kept open, and with several panes streaming at once. It installs as a separate product with its own shortcut, so it can run beside an older installation without touching its license, MetaTrader profiles or position state.

## Access

The terminal opens without a code, but it will not load new market data or accept new orders until a personal access code is activated. Existing positions can still be closed and protected without a code, so an expired key never traps you in a trade.

Codes are issued for 28 days by the official Telegram bot and are never published here:

**[Open @Tyumex_bot](https://t.me/Tyumex_bot)**

## Features

### Charts and data
- Multiple independent panes in one workspace, each with its own source, symbol and timeframe.
- Binance Spot, Binance USD-M Futures and Hyperliquid.
- Exchange API data for CME and MOEX instruments, including index futures such as NQ.
- Up to four local MetaTrader broker slots, MetaTrader 4 or MetaTrader 5, each pointed at your own installed terminal.
- Timeframes from 20s and 30s candles built out of ticks through 1m, 3m, 5m, 15m, 30m, 1h, 4h and 1D.
- Second-level history is filled from minute data on load, so a chart is usable immediately instead of waiting for ticks.
- Live streaming candles, session overlays and depth-style price levels.
- Cluster volume: traded volume per price inside each candle, with its own controls and labels that shrink to fit.
- Instrument catalog cached on disk, so symbol search stays usable when the data service is slow.

### Analysis
- Built-in SMA, EMA, RSI, MACD and Bollinger Bands.
- Twelve drawing tools shared across panes: trend line, ray, horizontal and vertical lines, rectangle, ellipse, triangle, arrow, text, measure, plus a selector and an eraser.
- One-shot mode returns to the cursor after a single drawing; the eraser clears a chart without hunting for individual objects.
- Drawings are anchored to price and time, so they survive timeframe and symbol switching.
- Palette color picker for chart and drawing colors.

### Trading through MetaTrader
- Market and pending orders, with pendings draggable directly on the chart.
- Position sizing from a fixed lot, a percentage of the deposit, or a cash amount.
- Stop-loss trade planner: draw the stop on the chart and the volume follows it. The stop itself can come from the extremum of the last three candles, a fixed number of points, or the plan drawn on the chart.
- Stop Loss and Take Profit set before the order is sent.
- Break-even shift and Safe Mode guards.
- Position and order management from the chart, including partial and full close.
- Bar replay simulator: replay history bar by bar with exchange-native order sizing and leverage, to rehearse an entry without risking an account.

![Tyumex Terminal workspace](docs/terminal-workspace.png)

## Access modes

| Mode | What it opens |
|---|---|
| Full | All features, trading on demo accounts. |
| Partner | Demo accounts plus one linked live account. |
| Viewer | Minute charts only; trading and closed features unavailable. |

The mode is re-checked every ten minutes. If a check cannot be completed, the terminal falls back to the narrowest mode rather than opening more than the honest one.

## Installation

1. Download `TyumexTerminalNextSetup-1.0.112.exe` from the [latest release](https://github.com/Tyumex/tyumex-trading-terminal/releases/latest) and check its SHA-256.
2. Run the installer. It installs into `%LOCALAPPDATA%\Programs\Tyumex Terminal Next` and creates a desktop shortcut, isolated from other Tyumex installations.
3. Start **Tyumex Terminal Next**.
4. For Binance, Hyperliquid and exchange API charts, pick the source and symbol in the chart header. Nothing else is required.
5. For MetaTrader charts, open settings and add the full path to your broker terminal: `terminal64.exe` for MetaTrader 5, `terminal.exe` for MetaTrader 4. The platform follows the file you pick. Keep that MetaTrader running and logged in.

Running a newer installer over an existing installation updates it in place. The license, MetaTrader profiles, workspace settings and managed-position state live under `%LOCALAPPDATA%\Tyumex Terminal\data` and survive updates.

No separate Python or Node.js installation is needed. Internet access is required for exchange data. MetaTrader data and trading require a locally installed and authorized MetaTrader 4 or MetaTrader 5 terminal.

## Requirements

- Windows 10 or 11, 64-bit.
- Internet connection for Binance, Hyperliquid and exchange API market data.
- MetaTrader 4 or MetaTrader 5, installed and logged in, for MetaTrader charts and trading.
- A personal access code from [@Tyumex_bot](https://t.me/Tyumex_bot).

## Security and privacy

- The application serves its interface on `127.0.0.1` only. Nothing is exposed to the local network.
- Requests are checked against DNS-rebinding attacks, so a web page cannot reach the terminal through your browser.
- A Content-Security-Policy header and CSRF checks protect the local interface.
- Broker credentials and API secrets are stored encrypted with Windows DPAPI, bound to your Windows account.
- Text coming from a broker is escaped everywhere it is displayed.
- Exchange market data works out of the box without any account of yours. To trade through the exchange API instead of MetaTrader, add your own token in settings and enable the personal token option.
- No trading credentials, account numbers or terminal paths leave your machine.

When reporting an issue, never post broker credentials, account numbers, license codes or local terminal paths, and blur them in screenshots.

## Notes

- Enter the exact symbol name used by your broker in MetaTrader. Broker naming differs.
- A MetaTrader 4 source has no market depth, so depth-style levels are not offered for it, and MT4 brokers publish no tick history: second-level bars are collected from the live stream while the terminal is open, and older bars come from M1.
- Buy and Sell controls send the order immediately. Check volume, Stop Loss and Take Profit before clicking.
- The terminal is a trading workspace, not a signal service. It gives no advice and guarantees no profit. All trading decisions and their outcomes are yours.

## License

Proprietary commercial software, not open source. The installer published here is licensed for personal use with an active access code; redistribution, resale, reverse engineering and modification are not permitted. See [LICENSE](LICENSE).

## Support

Access codes, current builds, activation questions and feedback: [@Tyumex_bot](https://t.me/Tyumex_bot).

---

<sub>Keywords: trading terminal, market terminal, multi-chart, Binance, Binance Futures, Hyperliquid, MetaTrader 4, MT4, MetaTrader 5, MT5, CME, MOEX, NQ, XAUUSD, tick charts, second charts, cluster volume, footprint, custom timeframes, bar replay, scalping, technical indicators, risk management, Windows trading software.</sub>
