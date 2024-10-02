# Объект
Перебор объекта циклом.

    <div v-for="value in country">{{ value }}</div>

    data: {
        country: { name: 'Россия', capital: 'Москва', domain: '.ru' },
    }


Выводим ключ и значение:

    <div v-for="(value, key) in country">{{ key }}: {{ value }}</div>

Вставляем имя ключа в атрибут `class`:
    
    <div v-for="(value, key) in country" v-bind:class="key">{{ key }}: {{ value }}</div>
