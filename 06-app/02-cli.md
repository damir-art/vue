# CLI
Установка CLI. Создание проекта. Нужно сначала установить `node.js`
- нужно установить расширение Visual Studio Code `Vetur`

Порядок установки https://cli.vuejs.org/ru/guide/installation.html:
- `npm install -g @vue/cli` установка vue
- `vue --version`           версия vue cli
- `vue create myapp`        создание приложения
- `Manually ...`            выбор ручной настройки
- `Linter / Formatter`      остальные убрать, их можно добавить потом
- `ESLint with ...`
- `Lint on save`
- `In package.json`
- `y`
- `enter`         не сохранять пресет (если попросят занести папку node_modules в .gitignore, то не надо, она туда поместится автоматически)
- `cd myapp`      перейти в проект в консоли
- `npm run serve` запустить проект
- `npm run build` когда приложение готово

Переходим в `src/App.vue` тут можно менять контент, который отображается на главной.
