# Tyumex Terminal Standard 1.0.144

Windows 10 / 11, 64-bit. Standard edition (`next`), without the Author deal-selection module.

## Изменения с 1.0.140

- Реплей стартует с выбранной даты календаря и забирает максимум истории, который даёт источник: MetaTrader и фьючерсная лента — до 200 000 баров, секундные MetaTrader — до 5 000, Binance — до 20 000, событийные бары — до 50 000. Загруженное число баров и диапазон дат видны в настройках реплея; при нехватке истории терминал объясняет, что доступно.
- Окно настроек получило меню разделов слева и отдельную прокручиваемую область настроек.
- Панель лицензии — круглая кнопка с логотипом вместо отдельной кнопки «Код доступа»; проверка связи показывает краткий результат. Журнал сделок запоминает выбранный период.

## Changes since 1.0.140

- Replay starts from a chosen calendar date and pulls the maximum history the source allows: MetaTrader and the futures feed up to 200,000 bars, MetaTrader seconds up to 5,000, Binance up to 20,000, event bars up to 50,000. The loaded bar count and date range are shown in the replay settings; when history falls short, the terminal explains what is available.
- The settings window got a section menu on the left and a scrollable settings area.
- The license panel is a round logo button instead of a separate access-code button; the connection check shows a brief result. The deals journal remembers its selected period.

## Download / Установка

Download `TyumexTerminalNextSetup-1.0.144.exe` from this release and run it over your existing Standard installation. Personal settings and access data are retained. / Скачайте установщик и запустите поверх текущего Стандарта. Персональные настройки и данные доступа сохраняются.

SHA-256:

```text
FE57E8CDDFBE9A51F0B4084AC5DFE0D3CC69D386D378ABE2C99A1D548D2F83E8
```

```powershell
Get-FileHash .\TyumexTerminalNextSetup-1.0.144.exe -Algorithm SHA256
```

Replay uses an OHLC execution model and provider-limited history. / Реплей использует модель исполнения OHLC; глубина истории ограничена источником.

[Browser demo / Демо](https://demo.tyumextrading.pro/) · [Website / Сайт](https://tyumextrading.pro/) · [Access and support / Доступ и поддержка](https://t.me/Tyumex_bot)
