# Tyumex Terminal Standard 1.0.175

**Цена, время и объём — от чтения рынка до тренировки сделки в одном терминале.**

Улучшения после публичной версии 1.0.158:

- **Больше контекста в каждом баре.** Экспериментальные Renko/Range объединяют движение цены и таймфрейм; адаптивный Renko «Поток цены и объёма» учитывает относительный объём сделок и показывает заполнение цели прямо в теле бара.
- **Кластерный анализ рядом с ценой.** Отдельные «Объёмные сигналы», профиль POC/VAH/VAL и опциональный звуковой алерт разворота по максимуму кластера в тени закрытого бара.
- **Глубокая история без остановки живого графика.** Фоновая загрузка тиков и более надёжная синхронизация холодной истории MT5. Задержанные тики учитываются при закрытии баров по времени ленты.
- **Более точная тренировка.** Секундный архивный реплей, дробный учебный объём и исправленные расчёты комиссий, риска и результата биржевой модели. Источник определяет доступную глубину истории.
- **Меньше лишних действий.** Переход к первому загруженному бару с сохранением масштаба, компактная ценовая шкала; отключённые объёмные сигналы не запускают лишний анализ.

## English

**Price, time and volume — market analysis and trade practice in one terminal.**

- Experimental time-and-price Renko/Range modes and adaptive price-and-volume Renko with in-bar volume progress.
- Dedicated volume signals, POC/VAH/VAL profiles and optional reversal alerts based on completed-bar cluster structure.
- Background tick-history loading while live updates continue; more reliable cold MT5 history synchronization and feed-time bar closure.
- Second-based archive replay, fractional training volume and corrected exchange training risk, commission and P/L calculations.
- Jump to the first loaded bar while keeping zoom; a narrower price scale and reduced work when volume signals are disabled.

## Установка / Installation

Windows 10/11, 64-bit. Standard (`next`), без авторского модуля подборки сделок.
Запустите установщик поверх текущего Стандарта; персональные настройки сохраняются.
Run the installer over your current Standard installation; personal settings are retained.

Файл / File: `TyumexTerminalNextSetup-1.0.175.exe`

SHA-256:

```text
E51B530E72DEE57F932238F0818BDFB9C6237BABCA21982A9711D325274B71AC
```

```powershell
Get-FileHash .\TyumexTerminalNextSetup-1.0.175.exe -Algorithm SHA256
```

Гибридные режимы экспериментальные; прибыльность не подтверждена. Объём биржевых сделок и число обновлений котировок различаются. История MT5 зависит от брокера и настроек терминала; год тиков не гарантируется. Hyperliquid удалён; сохранённые панели этого источника переходят на Binance Futures. Сохранённые удалённые варианты Renko/Range с ТФ переходят на соответствующее «Свободное тело + ТФ». Сигналы выключены по умолчанию для новых настроек.

Hybrid modes are experimental. Exchange trade volume differs from quote-update counts. MT5 history depth depends on the broker and terminal settings. Hyperliquid was removed; saved panels migrate to Binance Futures. Removed time-based Renko/Range variants migrate to the corresponding free-body mode. Volume signals default to off for new settings.

[Демо / Demo](https://demo.tyumextrading.pro/) · [Сайт / Website](https://tyumextrading.pro/) · [Доступ и поддержка / Access and support](https://t.me/Tyumex_bot)