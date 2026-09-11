# Tyumex Terminal Standard 1.0.140

Windows 10 / 11, 64-bit. Standard edition (`next`), without the Author deal-selection module.

## Изменения с 1.0.135

- Быстрее стартуют альтернативные графики: свежие бары и живые обновления приходят во время фоновой загрузки истории.
- Секундный биржевой реплей, исторические кластеры без раскрытия будущих баров и перемотка к заданному времени суток.
- Процент заполнения нетаймового бара, подписи совместимости источников и 500 баров истории по умолчанию для альтернативных графиков.
- Предварительные проверки ведомых в копировщике и исправления Safe / безубытка.
- Исправлена панель риска при смещении часов брокера. Лимит прибыли закрепляется после закрытия всех позиций; лимит убытка действует сразу.
- Сохранено привычное оформление.

## Changes since 1.0.135

- Alternative charts show fresh bars and live updates while deeper history loads in the background.
- Second-based exchange replay, historical clusters without revealing future bars, and a jump to a chosen time of day.
- Non-time bar completion percentages, source-compatibility labels and a default of 500 history bars for alternative charts.
- Follower prechecks in trade copying and fixes to Safe / break-even handling.
- Fixed risk-panel errors with broker clock offsets. The profit lock is confirmed after all account positions close; the loss limit applies immediately.
- Preserved the familiar appearance.

## Download / Установка

Download `TyumexTerminalNextSetup-1.0.140.exe` from this release and run it over your existing Standard installation. Personal settings and access data are retained. / Скачайте установщик и запустите поверх текущего Стандарта. Персональные настройки и данные доступа сохраняются.

SHA-256:

```text
DF7ECD1D0836D5D104AFA8F21B36D1BEBC223D17D81CB86C186C558BAA75EA03
```

```powershell
Get-FileHash .\TyumexTerminalNextSetup-1.0.140.exe -Algorithm SHA256
```

Replay uses an OHLC execution model and provider-limited history. Copying is sequential; a late broker rejection can leave only the master position open. Existing server-confirmed daily locks are not automatically removed.

Реплей использует модель исполнения OHLC; глубина истории ограничена источником. Копирование последовательное: поздний отказ брокера может оставить позицию только на мастере. Ранее закреплённые сервером дневные блокировки автоматически не снимаются.

[Browser demo / Демо](https://demo.tyumextrading.pro/) · [Website / Сайт](https://tyumextrading.pro/) · [Access and support / Доступ и поддержка](https://t.me/Tyumex_bot)
