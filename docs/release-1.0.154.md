# Tyumex Terminal Standard 1.0.154

Windows 10 / 11, 64-bit. Standard edition (`next`), without the Author deal-selection module.

## Изменения

- BTCUSDT, XAUUSDT и QQQUSDT Binance USD-M Futures используют латвийский архив настоящих свечей и сделок. Обычные свечи читаются из долговечного OHLC-архива, событийные графики и футпринт — из ленты сделок.
- Range, Delta, Reversal и другие событийные графики показывают промежуточную историю уже во время загрузки. Новые данные объединяются с историей без повторов и потери текущей цены.
- Для Binance и Bybit секундные свечи собираются из настоящих сделок. Отсутствующая тиковая история не подменяется искусственным движением внутри минутной свечи.
- Улучшены симулятор, расчёт риска и Safe. Недостаточный объём больше не увеличивается автоматически; поддерживаемые USDT-фьючерсы могут сопровождаться автоматическим Safe по подтверждённому исполнению.
- Автоматические снимки всего рабочего пространства при открытии, приближении к SL/TP и закрытии сделки сохранены. Функция выключена по умолчанию.

## Changes

- BTCUSDT, XAUUSDT and QQQUSDT Binance USD-M Futures use the Latvia archive of real candles and trades. Ordinary candles read the durable OHLC archive; event bars and footprints use the trade tape.
- Range, Delta, Reversal and other event-driven charts publish partial history while loading. Live data is reconciled with history without duplicates or replacing the current quote.
- Binance and Bybit second candles are built from real trades. Missing tick history is never replaced with a fabricated path inside minute candles.
- Replay, risk sizing and Safe handling were tightened. Sub-minimum size is no longer silently increased; supported USDT futures can use automatic Safe after confirmed execution.
- Automatic full-workspace screenshots at entry, near SL/TP and at close remain available and are off by default.

## Package

`TyumexTerminalNextSetup-1.0.154.exe`

SHA-256:

```text
EFD846341B126A14DBFF4ECCAB370F4E8C8CD2E4B2ABFC87912B29EA6860BD80
```

Install over the existing Standard copy to update in place. License data, MetaTrader profiles, workspace settings and managed-position state are retained.
