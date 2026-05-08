# Edinstvo Domain Wrapper

Отдельная папка под отдельный репозиторий для доменного URL сайта `ЕДИНСТВО`.

## Что это

Статический wrapper-сайт, который:

- открывается по вашему домену;
- встраивает Google Apps Script Web App через `iframe`;
- прокидывает query-параметры в `.../exec`;
- готов для деплоя в Timeweb App Platform как отдельный frontend-репозиторий.

## Файлы

- `index.html` - доменная оболочка поверх GAS
- `package.json` - минимальная сборка через Vite

## Что нужно заменить перед деплоем

Сейчас в `index.html` зашит URL:

`https://script.google.com/macros/s/AKfycby1S6ZSi3rWvsJGzi2hJtgUc956Wm4guD8cDAYa9zx-8ZpxEwk_-4D6iLllNpc1rw/exec`

Если будет новый deployment, замените URL в `index.html`.

## Как залить в GitHub

1. Инициализировать git в этой папке.
2. Создать отдельный репозиторий.
3. Запушить содержимое.

## Как деплоить в Timeweb App Platform

1. Создать новое `Frontend` приложение.
2. Подключить этот репозиторий и ветку.
3. Команда сборки:

```bash
npm run build
```

4. Build directory:

```text
dist
```

## Важно

В вашем Apps Script уже включен `HtmlService.XFrameOptionsMode.ALLOWALL`, поэтому такой wrapper-сценарий допустим для встраивания сайта в `iframe`.
