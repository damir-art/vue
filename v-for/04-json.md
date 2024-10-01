# JSON
Перебор JSON-объекта циклом.

    <div v-for="(value, key) in cities" v-bind:class="value">{{ key }}: {{ value.name }}, {{ value.domain }}</div>

    data: {
        // cities: ['Москва', 'Берлин', 'Париж'],
        // country: { name: 'Россия', capital: 'Москва', domain: '.ru' },
        cities: [
            {
                name: 'Москва',
                domain: '.ru',
            },
            {
                name: 'Берлин',
                domain: '.de',
            },
            {
                name: 'Париж',
                domain: '.fr',
            },
        ]
    }
