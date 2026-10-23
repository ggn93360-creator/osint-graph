# OSINT Graph

Интерактивный граф инструментов OSINT (Open Source Intelligence), inspired by osint-catalog.org/graph.

## Возможности

- **Интерактивная сеть** — инструменты связаны в категории
- **Фильтры по категориям** — Network, Intelligence, Malware, Web
- **Поиск** — Найдите инструмент по названию или описанию
- **Подробная информация** — Кликните на любой инструмент для деталей
- **Переключение языков** — RU/EN
- **Тёмная тема** — Подходит для работы в ночное время

## Как запустить локально

1. Клонируйте или скачайте файл `osint-graph-site.html`
2. Откройте файл в браузере: `open osint-graph-site.html` или перенесите его в папку веб-сервера
3. Все функционал доступен без бакенда — всё работает entirely на клиенте

## Как опубликовать на GitHub Pages

### Способ 1: Через GitHub Interface

1. Создайте новый репозиторий на GitHub: `osint-graph-site` (или любое другое название)
2. Загрузите файл `osint-graph-site.html` в репозиторий
3. Перейдите в настройки репозитория (Settings)
4. В разделе "Code and automation" выберите "Pages"
5. В разделе "Source" выберите ветку `main` и папку `/ (root)`
6. Сайт будет доступен по адресу: `https://ваш username>.github.io/osint-graph-site/`

### Способ 2: Через GitHub CLI

```bash
# Создайте репозиторий
gh repo create osint-graph-site --public

# Загрузите файл
git add osint-graph-site.html
git commit -m "Initial commit: OSINT Graph site"
git push origin main

# Включите GitHub Pages
gh pages enable main --source /root
```

## Структура файла

Файл `osint-graph-site.html` содержит:
- Полностью самодостаточный HTML (никаких внешних зависимостей, кроме CDN Tailwind)
- Встроенные данные о инструментах OSINT (20 инструментов в 4 категориях)
- CSS анимации и интерактивность
- Адаптивный дизайн для мобильных устройств

## Данные

Сайт включает 20 популярных OSINT-инструмента через следующие категории:

- **Network** (Сеть): Shodan, Censys, Fofa, Nmap, Masscan, ZMap
- **Intelligence** (Интеллект): PassiveTotal, AbuseIPDB, OTX Alienvault, Greynoise, Recon-ng
- **Malware** (Мальвар): VirusTotal, Any.Run, Hybrid Analysis
- **Web** (Web): URLScan.io, BuiltWith, Wappalyzer, Fiddler, Burp Suite, Nikto

## Настройка

Чтобы добавить больше инструментов, редактируйте массив `toolsData` в `<script>` секции. Для добавления новых категорий обновите:
- Массив `categories`
- Углы позиционирования
- Кнопки фильтров в HTML