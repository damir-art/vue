# Реактивность данных
Реактивность данных во Vue.js относится к способности фреймворка автоматически отслеживать изменения в данных и соответствующим образом обновлять пользовательский интерфейс.

v-model="name"

    <div class="sample">
      <h2>Привет это Vue</h2>
      <div>
        Имя: {{ name }}
      </div>
      <div>
        <input type="text" v-model="name">
      </div>
    </div> <!-- sample -->

    let sample = Vue.createApp({
      data() {
        return {
          name: 'Damir'
        }
      }
    }).mount('.sample');

Если ввести в консоли `sample` то выведет экземпляр vue. Смысл реактивности заключается в том что, к этому экземпляру можно обратиться по интересующемуся ключу если в консоли после sample поставить точку.

    sample.name = 123 // name изменится

Это всё меняется за счет геттеров и сеттеров. При этом директива `v-model` это обычный JavaScript.

## Что такое реактивность данных
Реактивность данных во Vue.js относится к способности фреймворка автоматически отслеживать изменения в данных и соответствующим образом обновлять пользовательский интерфейс. Когда данные изменяются, Vue эффективно определяет, какие компоненты необходимо повторно отобразить, чтобы пользовательский интерфейс оставался синхронизированным с базовыми данными.

Vue обеспечивает реактивность данных благодаря комбинации механизма получения/установки (get/set) в JavaScript, системы отслеживания зависимостей и виртуального DOM. Синтаксис и подход к включению реактивности в Vue просты и интуитивно понятны.

Чтобы сделать свойство данных реактивным, вы определяете его в параметре data экземпляра Vue или используете функцию reactive из Vue Composition API. Vue автоматически преобразует каждое свойство в реактивный метод получения/установки в процессе инициализации.

Когда свойство данных становится реактивным, вы можете получить к нему доступ в своем шаблоне или компонентных методах, и Vue автоматически отследит зависимости. Когда во время рендеринга осуществляется доступ к реактивному свойству, Vue знает, что оно должно быть включено в график зависимостей для этого компонента.

Этот механизм позволяет Vue.js эффективно обновлять пользовательский интерфейс при изменении базовых данных, обеспечивая тем самым синхронизацию между представлением и моделью данных.

Фигурные скобки `{{ }}` используются для интерполяции выражений в шаблонах Vue. Они позволяют отображать значения переменных и свойств компонентов в HTML. Однако, это лишь один из аспектов работы с данными в Vue.js, который связан с реактивностью, но не является её определением.

Реактивность данных в Vue.js достигается за счёт использования механизма получения/установки (getter/setter) в JavaScript, системы отслеживания зависимостей и виртуального DOM.

## Пример реактивности данных
Вот простой пример реактивности данных во Vue.js с использованием Options API:

    <template>
      <div id="app">
        <h1>{{ title }}</h1>
        <button @click="increment">Increment</button>
      </div>
    </template>

    <script>
      export default {
        name: 'App',
        data() {
          return {
            title: 'Hello World!'
          }
        },
        methods: {
          increment() {
            this.title += '!';
          }
        }
      }
    </script>

В этом примере мы определяем свойство title в объекте data, делая его реактивным. Затем мы используем метод increment, который изменяет значение title, добавляя восклицательный знак. Поскольку title является реактивным свойством, изменение его значения внутри метода increment автоматически обновляет пользовательский интерфейс, отображая новое значение в заголовке.
