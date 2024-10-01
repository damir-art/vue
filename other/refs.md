# $refs
`$refs` используется для обращения к DOM напрямую при поддержки старых проектов, например там где есть jQuery.

- `$refs` объект содержащий в себе все элементы к которым можно обратиться по значению их `ref`
- `$refs` не рекомендуется использовать

Обращаемся к DOM-элементу напрямую, изменяем подзаголовок:

    <div id="app">
        <h1 ref="zagolovok">{{ title }}</h1>
        <h2 ref="podzagolovok">{{ subTitle }}</h2>

        <button type="button" @click="changeH1">Кнопка</button>
    </div>

    const app = new Vue({
        el: '#app',
        data: {
            title: 'Заголовок',
            subTitle: 'Подзаголовок приложения',
        },
        methods: {
            changeH1() {
                console.log(this.$refs)
                this.$refs.zagolovok.textContent = 'Изменили заголовок!'
            }
        }
    })
