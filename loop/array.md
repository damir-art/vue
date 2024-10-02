# Массив
Перебор массива циклом.

    <div v-for="value in cities">{{ value }}</div>

    data: {
        cities: ['Москва', 'Берлин', 'Париж'],
    }

Выводим индекс и значение:

    <div v-for="(value, index) in cities">{{ index }}: {{ value }}</div>
    <div v-for="(value, index) in cities">{{ index + 1 }}: {{ value }}</div>
