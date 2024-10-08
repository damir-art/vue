# mount
В контексте Vue.js, метод `mount` используется для внедрения (монтирования) экземпляра Vue в существующий элемент DOM. Это один из способов начальной загрузки приложения Vue в HTML-документ.

Пример использования:

    import { createApp } from 'vue';

    const app = createApp({
      // Ваш компонент Vue здесь
    });

    app.mount('#app'); // Монтирование экземпляра Vue в элемент с id="app"

В этом примере создается экземпляр Vue с помощью `createApp`, а затем он монтируется в элемент с идентификатором #app. Это позволяет Vue управлять содержимым этого элемента и отображать его согласно логике вашего приложения.

## Старая запись
Другой способ создания приложения (не рекомендоуется).

    <div id="app"></div>

    <script src="js/vue.js"></script>

    <script>
        const app = new Vue({
            data: {
                title: 'Заголовок через $mount',
            },
            template: '<h1>{{ title }}</h1>'
        })

        app.$mount('#app')
    </script>
