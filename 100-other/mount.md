# mount
Другой способ создания приложения. Не рекомендоуется.

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
