# Установка
Установить Vue можно через CDN или npm. Также можно сделать первые сценарии в печочницах: https://ru.vuejs.org/guide/quick-start.html

## CDN
https://ru.vuejs.org/guide/quick-start.html#using-vue-from-cdn

    <script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>

Как модуль:

    import { createApp } from 'https://unpkg.com/vue@3/dist/vue.esm-browser.js'

Файл по ссылке CDN можно скачать и разместить на хостинге, так будет быстрее работать.  
Если Vue установлен как обычный файл, а не сборка через npm, то в этом случае не получится использовать синтаксис однофайловых компонентов (SFC).

## Установка Vue
Установка Vue.js через консоль: https://ru.vuejs.org/guide/quick-start.html#creating-a-vue-application

- переходим в терминале в папку
- вводим код `npm create vue@latest`
- нажимаем `y` энтер
- пишем название проекта например `vue-project`
- добавляем TypeScript? Yes/No (n)
- добавляем JSX? Yes/No (n)
- Добавляем роутер? Yes/No (n)
- Добавляем Пиниа? Yes/No (n)
- Добавляем Витест? Yes/No (n)
- Добавляем Энд? Yes/No (n)
- Добавляем Еэслинт? Yes/No (n)
- Добавляем Девтулс? Yes/No (n)

Когда проект устновится вам скажут, что для запуска проекта вам надо набрать следующие команды:

  cd vue-project
  npm install // ждем когда загрузит файлы
  npm run dev // разработка, открываем в браузере адрес Local:
  // читай project/vue-project/README.md
  npm run build // продакшен

Откроется сайт, чья страница основана на компоненте `src/App.vue`  
Перейдя в VSC в этот файл вам предлжат установить расширение `Vue - Official`  
Про устройства компонентов можете прочитать тут: `component/`

## Плагины для Vue
- https://github.com/vuejs/awesome-vue

## Разное
- плагин для браузера `Vue Devtools`
