# Tyumex Terminal

Windows desktop multi-chart trading terminal for Binance and MetaTrader 5 (MT5), with tick-built 20–45-second charts, technical analysis and risk-based chart trading. One workspace holds several independent chart panes, each on its own data source: Binance Spot, Binance USD-M Futures, an exchange data API for CME and MOEX instruments, and local MetaTrader 5 terminals. Orders are sent to MT5 directly from the chart.

This repository publishes the **Standard Edition** installer, screenshots and setup notes. Application sources are not part of the public package.

[Русская версия -> README.ru.md](README.ru.md)

![Tyumex Terminal overview](docs/terminal-overview.png)

## Download

| | |
|---|---|
| Version | **1.0.91** |
| Package | `TyumexTerminalStandardSetup-1.0.91.exe` |
| SHA-256 | `DFFFE30E2B3F6FCA94D6C5FE47B86E8903A430B03EDBC3546F724AE6EC11CAB5` |
| Platform | Windows 10 / 11, 64-bit |

**[Download the latest release](https://github.com/Tyumex/tyumex-trading-terminal/releases/latest)**

Verify the download before running it:

```powershell
Get-FileHash .\TyumexTerminalStandardSetup-1.0.91.exe -Algorithm SHA256
```

The printed hash must match the SHA-256 above. If it does not, do not run the file.

## Access

The terminal opens without a code, but it will not load new market data or accept new orders until a personal access code is activated. Existing positions can still be closed and protected without a code, so an expired key never traps you in a trade.

Codes are issued for 28 days by the official Telegram bot and are never published here:

**[Open @Tyumex_bot](https://t.me/Tyumex_bot)**

## Features

### Charts and data
- Multiple independent panes in one workspace, each with its own source, symbol and timeframe.
- Binance Spot and Binance USD-M Futures.
- Exchange API data for CME and MOEX instruments, including index futures such as NQ.
- Local MetaTrader 5 terminals, two broker slots preconfigured (Tickmill, Just2Trade) and two free slots for your own.
- Native sub-minute aggregation: 20s, 30s and 45s candles built from ticks, alongside 1m, 3m, 5m, 15m, 30m, 1h, 4h and 1D.
- Live streaming candles, volume, session overlays and depth-style price levels.

### Analysis
- Built-in SMA, EMA, RSI, MACD and Bollinger Bands.
- Drawing toolbar shared across panes: trend line, ray, horizontal line, rectangle, arrow and text.
- Drawings stay attached to price and time, so they survive timeframe and symbol switching.

### Trading through MT5
- Market and pending orders with risk-based or fixed volume sizing.
- Stop Loss and Take Profit set before the order is sent.
- Pending orders draggable directly on the chart.
- Break-even shift and Safe Mode guards.
- Position and order management from the chart, including partial and full close.

![Tyumex Terminal workspace](docs/terminal-workspace.png)

## Installation

1. Download `TyumexTerminalStandardSetup-1.0.91.exe` from the [latest release](https://github.com/Tyumex/tyumex-trading-terminal/releases/latest) and check its SHA-256.
2. Run the installer. It creates a desktop shortcut and installs into `%LOCALAPPDATA%\Programs\Tyumex Terminal`, isolated from other Tyumex installations.
3. Start **Tyumex Terminal Standard**.
4. For Binance and exchange API charts, pick the source and symbol in the chart header. Nothing else is required.
5. For MT5 charts, open settings, add the full path to the 64-bit `terminal64.exe` of the broker you use, and keep that MT5 terminal running and logged in.

Running a newer installer over an existing installation updates it in place. The license, MT5 profiles, browser profile and managed-position state live under `%LOCALAPPDATA%\Tyumex Terminal` and survive updates.

No separate Python or Node.js installation is needed. Internet access is required for exchange data. MT5 data and trading require a locally installed and authorized MetaTrader 5 terminal.

## Requirements

- Windows 10 or 11, 64-bit.
- Internet connection for Binance and exchange API market data.
- MetaTrader 5, 64-bit, installed and logged in, for MT5 charts and trading.
- A personal access code from [@Tyumex_bot](https://t.me/Tyumex_bot).

## Security and privacy

- The application serves its interface on `127.0.0.1` only. Nothing is exposed to the local network.
- Requests are checked against DNS-rebinding attacks, so a web page cannot reach the terminal through your browser.
- A Content-Security-Policy header and CSRF checks protect the local interface.
- Broker credentials and API secrets are stored encrypted with Windows DPAPI, bound to your Windows account.
- Exchange market data works out of the box without any account of yours. To trade through the exchange API instead of MT5, add your own token in settings and enable the personal token option.
- No trading credentials, account numbers or terminal paths leave your machine.

When reporting an issue, never post broker credentials, account numbers, license codes or local terminal paths, and blur them in screenshots.

## Notes

- Enter the exact symbol name used by your broker in MT5. Broker naming differs.
- Buy and Sell controls send the order immediately. Check volume, Stop Loss and Take Profit before clicking.
- The Standard Edition is a trading workspace, not a signal service. It gives no advice and guarantees no profit. All trading decisions and their outcomes are yours.

## License

Proprietary commercial software, not open source. The installer published here is licensed for personal use with an active access code; redistribution, resale, reverse engineering and modification are not permitted. See [LICENSE](LICENSE).

## Support

Access codes, current builds, activation questions and feedback: [@Tyumex_bot](https://t.me/Tyumex_bot).

---

<sub>Keywords: trading terminal, market terminal, multi-chart, Binance, Binance Futures, MetaTrader 5, MT5, CME, MOEX, NQ, XAUUSD, tick charts, second charts, custom timeframes, scalping, technical indicators, risk management, Windows trading software.</sub>
