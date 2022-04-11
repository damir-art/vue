# data
Данные во Vue.js

Свойство `data`, также является и объектом, может хранить в себе множество различных значений. Эти значения могут взаимодействовать друг с другом как в инстансе `new Vue` так и в шаблоне `id="app"`.

    data: {
        name: 'Иван',
        surname: 'Петров',
        age: 25
    }

Выводим значение свойства `name` из объекта `data`:

    <div id="app">
        <h1>{{ name }}</h1>
    </div>

Выводим информацию которая хранит в себе `data`:

    {{ $data }} // { "name": "Иван", "surname": "Иванов", "age": 21 }