# INTERCEPT

<p align="center">
  <img src="https://img.shields.io/badge/python-3.9+-blue.svg" alt="Python 3.9+">
  <img src="https://img.shields.io/badge/license-MIT-green.svg" alt="MIT License">
  <img src="https://img.shields.io/badge/platform-macOS%20%7C%20Linux-lightgrey.svg" alt="Platform">
</p>

<p align="center">
  <strong>Платформа радиотехнической разведки</strong><br>
  Веб-интерфейс для инструментов радиоперехвата.
</p>

<p align="center">
  <img src="static/images/screenshots/screenshot2.png" alt="Скриншот">
</p>

---

## Что такое INTERCEPT?

INTERCEPT предоставляет единый веб-интерфейс для радиоинженерных инструментов:

- **Декодирование пейджеров** — POCSAG/FLEX через rtl_fm + multimon-ng
- **Датчики на 433 МГц** — метеостанции, TPMS, IoT через rtl_433
- **Отслеживание воздушных судов** — ADS-B через dump1090 с онлайн-картой
- **Отслеживание спутников** — прогноз пролётов по TLE
- **Wi‑Fi разведка** — сканирование в режиме мониторинга через aircrack-ng
- **Сканирование Bluetooth** — обнаружение устройств и трекеров

---

## Сообщество

<p align="center">
  <a href="https://discord.gg/z3g3NJMe">Присоединяйтесь к нашему Discord</a>
</p>

---

## Быстрый старт

```bash
git clone https://github.com/smittix/intercept.git
cd intercept
./setup.sh
sudo python3 intercept.py
```

Откройте в браузере http://localhost:5050.

> **Важно:** требуется Python 3.9+ и внешние утилиты. См. [Hardware & Installation](docs/HARDWARE.md).

### Прокси и настройки безопасности

Внешние запросы (например, обновления TLE для спутников) используют стандартные переменные окружения прокси. Установите любые из них перед запуском приложения:

- `INTERCEPT_HTTP_PROXY` / `HTTP_PROXY`
- `INTERCEPT_HTTPS_PROXY` / `HTTPS_PROXY`
- `INTERCEPT_FTP_PROXY` / `FTP_PROXY`
- `INTERCEPT_SOCKS_PROXY` / `SOCKS_PROXY`

Дополнительно вы можете настроить сетевые ограничения для запросов TLE:

- `INTERCEPT_TLE_ALLOWED_HOSTS` — список разрешённых хостов через запятую (по умолчанию: домены CelesTrak)
- `INTERCEPT_TLE_REQUEST_TIMEOUT` — таймаут запроса в секундах (по умолчанию: `10`)
- `INTERCEPT_TLE_MAX_RESPONSE_SIZE` — максимальный размер ответа в байтах (по умолчанию: `1048576`)
- `INTERCEPT_TLE_USER_AGENT` — пользовательский заголовок User-Agent

Принимаются как верхний, так и нижний регистр переменных прокси.

---

## Требования

- **Python 3.9+**
- **SDR-оборудование** — RTL-SDR (~$25), LimeSDR или HackRF
- **Внешние утилиты** — rtl-sdr, multimon-ng, rtl_433, dump1090, aircrack-ng

Быстрая установка (Ubuntu/Debian):
```bash
sudo apt install rtl-sdr multimon-ng rtl-433 dump1090-mutability aircrack-ng bluez
```

Подробности в [Hardware & Installation](docs/HARDWARE.md).

---

## Документация

| Документ | Описание |
|----------|----------|
| [Features](docs/FEATURES.md) | Полный список возможностей |
| [Usage Guide](docs/USAGE.md) | Детальные инструкции по режимам |
| [Troubleshooting](docs/TROUBLESHOOTING.md) | Решения распространённых проблем |
| [Hardware & Installation](docs/HARDWARE.md) | SDR-оборудование и установка инструментов |

---

## Разработка

Проект создан при участии ИИ как помощника по разработке. Цель — сделать Software Defined Radio доступнее за счёт чистого, единого интерфейса для популярных SDR-инструментов.

Приветствуются вклад и улучшения.

---

## Отказ от ответственности

**ПО предназначено только для образовательных целей.**

- Используйте только с надлежащим разрешением
- Перехват коммуникаций без согласия может быть незаконным
- Атаки на Wi‑Fi/Bluetooth требуют явного разрешения
- Вы сами отвечаете за соблюдение применимых законов

---

## Лицензия

Лицензия MIT — см. [LICENSE](LICENSE)

## Автор

Создано **smittix** — [GitHub](https://github.com/smittix)

## Благодарности

[rtl-sdr](https://osmocom.org/projects/rtl-sdr/wiki) |
[multimon-ng](https://github.com/EliasOenal/multimon-ng) |
[rtl_433](https://github.com/merbanan/rtl_433) |
[dump1090](https://github.com/flightaware/dump1090) |
[aircrack-ng](https://www.aircrack-ng.org/) |
[Leaflet.js](https://leafletjs.com/) |
[Celestrak](https://celestrak.org/)
