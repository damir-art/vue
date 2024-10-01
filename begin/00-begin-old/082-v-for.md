# Директива v-for
v-for директива для создания цикла.

## Массив
Обходим циклом массив, создаём несколько элементов списка:

    <ul>
        <li v-for="el in arr">{{ el }}</li>
    </ul>

    var app = new Vue({
        el: '#app',
        data: {
            arr: [
                'element 1',
                'element 2',
                'element 3'
            ]
        }
    })

`el` и `arr` пользовательские имена.

## Объект
Обходим циклом объект:

    <ul>
        <li v-for="el in obj">{{ el }}</li>
    </ul>

    obj: {
        name: 'Имя',
        surname: 'Фамилия',
        age: 25
    }

## JSON
Обходим циклом JSON, массив элементы которого объекты, выводим в таблице, разметка Pug:

    table(border="2")
        tr(v-for="el in json")
            td {{ el.name }}
            td {{ el.surname }}
            td {{ el.age }}

    json: [
        {
            name: 'Имя',
            surname: 'Фамилия',
            age: 25
        },
        {
            name: 'Имя 2',
            surname: 'Фамилия 2',
            age: 30
        },
        {
            name: 'Имя 3',
            surname: 'Фамилия 3',
            age: 35
        }
    ]
